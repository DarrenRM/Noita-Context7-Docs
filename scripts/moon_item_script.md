---
title: Moon Item Script
category: scripts
---

# Moon Item Script

This script defines the behavior of the "Moon" item in Noita, primarily focusing on its gravitational pull and floating mechanics.

## Key Attributes & Mechanics

### Gravitational Attraction

The Moon exerts a gravitational force on nearby projectiles and physics bodies.

*   **`distance_full`**: The maximum distance at which the Moon's gravity is fully effective (96 units).
*   **`gravity_coeff`**: A multiplier for the gravitational force (196).
*   **Attraction Logic**:
    *   Calculates the distance to affected entities.
    *   Applies a force inversely proportional to the distance, diminishing as entities get closer.
    *   Specifically targets entities tagged with "projectile".
    *   Applies a scaled force to physics bodies based on their mass.

### Floating Mechanism

The Moon uses raycasting to maintain a stable altitude.

*   **`float_range`**: The maximum distance the Moon attempts to "float" upwards (50 units).
*   **`float_force`**: The magnitude of the upward force applied for floating (3 units).
*   **`float_sensor_sector`**: Defines a cone for the raycast to detect platforms, preventing it from getting stuck on ceilings.
*   **Raycasting**: Casts a ray downwards to detect platforms. If a platform is hit, an opposing force is applied to keep the Moon at a certain distance from it.

### Physics Interaction

*   **`PhysicsApplyForceOnArea`**: Used to apply the gravitational force to physics bodies within a defined area around the Moon.
*   **`PhysicsApplyForce`**: Used to apply the floating force to the Moon itself.

## Code Structure

The script is organized into several key sections:

1.  **Initialization**: Sets up global variables for gravitational and floating parameters.
2.  **Camera Bounds Check**: Ensures the script only runs when the Moon is within the camera's view to optimize performance.
3.  **`calculate_force_at` Function**: A helper function to compute the gravitational force vector at a given point.
4.  **Projectile Attraction**: Iterates through nearby projectiles and applies gravitational force to their velocity.
5.  **Physics Body Attraction**: Defines a `calculate_force_for_body` function and uses `PhysicsApplyForceOnArea` to attract physics bodies.
6.  **Floating Logic**: Implements the raycasting and force application for maintaining altitude.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local distance_full = 96
local float_range = 50
local float_force = 3
local float_sensor_sector = math.pi * 0.3

local entity_id = GetUpdatedEntityID()
local x, y, rot = EntityGetTransform( entity_id )

if is_in_camera_bounds(x,y,250) then
	-- Function to calculate gravitational force
	function calculate_force_at(body_x, body_y)
		local distance = math.sqrt( ( x - body_x ) ^ 2 + ( y - body_y ) ^ 2 )
		if distance < 12 then
			-- Stop attracting when near enough to prevent collisions
			return 0,0
		end
		local direction = 0 - math.atan2( ( y - body_y ), ( x - body_x ) )

		local gravity_percent = ( distance_full - distance ) / distance_full
		local gravity_coeff = 196
		
		local fx = math.cos( direction ) * ( gravity_coeff * gravity_percent )
		local fy = -math.sin( direction ) * ( gravity_coeff * gravity_percent )

	    return fx,fy
	end

	-- Attract projectiles
	local entities = EntityGetInRadiusWithTag(x, y, distance_full, "projectile")
	for _,id in ipairs(entities) do	
		local physicscomp = EntityGetFirstComponent(id, "PhysicsBody2Component") or EntityGetFirstComponent( id, "PhysicsBodyComponent")
		if physicscomp == nil then -- velocity for physics bodies is done later
			local px, py = EntityGetTransform( id )

			local velocitycomp = EntityGetFirstComponent( id, "VelocityComponent" )
			if ( velocitycomp ~= nil ) then
				local fx, fy = calculate_force_at(px, py)
				edit_component( id, "VelocityComponent", function(comp,vars)
					local vel_x,vel_y = ComponentGetValue2( comp, "mVelocity")
					
					vel_x = vel_x + fx
					vel_y = vel_y + fy

					ComponentSetValue2( comp, "mVelocity", vel_x, vel_y)
				end)
			end
		end
	end


	-- Force field for physics bodies
	function calculate_force_for_body( entity, body_mass, body_x, body_y, body_vel_x, body_vel_y, body_angular )
		local fx, fy = calculate_force_at(body_x, body_y)

		fx = fx * 0.11 * body_mass
		fy = fy * 0.11 * body_mass

	    return body_x,body_y,fx,fy,0 -- forcePosX,forcePosY,forceX,forceY,forceAngular
	end
	local size = distance_full * 0.5
	PhysicsApplyForceOnArea( calculate_force_for_body, entity_id, x-size, y-size, x+size, y+size )
end

-- Float by raycasting down and applying opposite physical force
do
	local dir_x = 0
	local dir_y = float_range
	dir_x, dir_y = vec_rotate(dir_x, dir_y, ProceduralRandomf(x, y + GameGetFrameNum(), -float_sensor_sector, float_sensor_sector))
	
	local did_hit,hit_x,hit_y = RaytracePlatforms( x, y, x + dir_x, y + dir_y )
	if did_hit then
		local dist = get_distance(x, y, hit_x, hit_y)
		dist = math.max(6, dist) -- tame a bit on close encounters
		dir_x = -dir_x / dist * float_force
		dir_y = -dir_y / dist * float_force
		PhysicsApplyForce(entity_id, dir_x, dir_y)
	end
end
```