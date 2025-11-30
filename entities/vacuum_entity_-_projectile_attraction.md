---
title: Vacuum Entity - Projectile Attraction
category: entities
---

# Vacuum Entity - Projectile Attraction

This entity creates a vacuum effect that attracts projectiles and applies a force to physics bodies within its radius.

## Core Functionality

### Projectile Attraction

The entity scans for entities tagged as "projectile" within a `distance_full` (128 units). For each projectile found, it calculates a force directed towards the vacuum's center. This force is applied to the projectile's velocity, pulling it in.

-   **`distance_full`**: The radius within which projectiles are affected (default: 128).
-   **`calculate_force_at(body_x, body_y)`**: A helper function to determine the force vector and magnitude based on the distance from the vacuum.
    -   The force is stronger the closer the projectile is to the vacuum.
    -   The force is applied in the direction *towards* the vacuum.

### Physics Body Force Field

The entity also applies a general force to physics bodies within a specified area around it. This force is proportional to the body's mass and is also directed towards the vacuum.

-   **`calculate_force_for_body(...)`**: This function is called by `PhysicsApplyForceOnArea` for each physics body.
    -   It calculates the base force using `calculate_force_at`.
    -   The force is scaled by `0.2 * body_mass`.
    -   It returns the position, force components (X, Y), and angular force (which is 0 in this case).
-   **`PhysicsApplyForceOnArea(...)`**: This function applies the calculated force to physics bodies within a square area defined by `size` around the vacuum entity.
    -   **`size`**: Half the side length of the square area affected by the force field (calculated as `distance_full * 0.5`).

## Key Attributes

-   **`distance_full`**: Defines the primary range of the vacuum's influence.
-   **`gravity_coeff`**: A multiplier for the force applied to projectiles (default: 80).
-   **`0.2`**: A scaling factor for the force applied to physics bodies.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local distance_full = 128 -- Radius of influence for projectiles

local entity_id = GetUpdatedEntityID()
local x, y, rot = EntityGetTransform( entity_id ) -- Get the vacuum's position

-- Function to calculate the force vector towards the vacuum
function calculate_force_at(body_x, body_y)
	local distance = math.sqrt( ( x - body_x ) ^ 2 + ( y - body_y ) ^ 2 )
	local direction = 0 - math.atan2( ( y - body_y ), ( x - body_x ) ) -- Angle towards the vacuum

	local gravity_percent = ( distance_full - distance ) / distance_full -- How close the body is (0 to 1)
	local gravity_coeff = 80 -- Strength multiplier

	local fx = math.cos( direction ) * ( gravity_coeff * gravity_percent * -1) -- Force X component
	local fy = -math.sin( direction ) * ( gravity_coeff * gravity_percent * -1) -- Force Y component

    return fx,fy
end

-- Attract projectiles
local entities = EntityGetInRadiusWithTag(x, y, distance_full, "projectile")
for _,id in ipairs(entities) do
	-- Get physics component, prioritizing PhysicsBody2Component
	local physicscomp = EntityGetFirstComponent(id, "PhysicsBody2Component") or EntityGetFirstComponent( id, "PhysicsBodyComponent")
	-- Ensure it's not a black hole and has a physics component
	if physicscomp == nil and not EntityHasTag(id,"black_hole") then
		local px, py = EntityGetTransform( id ) -- Projectile position

		local velocitycomp = EntityGetFirstComponent( id, "VelocityComponent" )
		if ( velocitycomp ~= nil ) then -- If projectile has velocity
			local fx, fy = calculate_force_at(px, py) -- Calculate attraction force
			edit_component( id, "VelocityComponent", function(comp,vars)
				local vel_x,vel_y = ComponentGetValue2( comp, "mVelocity")

				vel_x = vel_x + fx -- Apply force to velocity
				vel_y = vel_y + fy

				ComponentSetValue2( comp, "mVelocity", vel_x, vel_y)
			end)
		end
	end
end

-- Apply force field to physics bodies
function calculate_force_for_body( entity, body_mass, body_x, body_y, body_vel_x, body_vel_y, body_angular )
	local fx, fy = calculate_force_at(body_x, body_y) -- Base force calculation

	fx = fx * 0.2 * body_mass -- Scale force by mass and a coefficient
	fy = fy * 0.2 * body_mass

    return body_x,body_y,fx,fy,0 -- Return position, force, and 0 angular force
end
local size = distance_full * 0.5 -- Define the area for force application
PhysicsApplyForceOnArea( calculate_force_for_body, entity_id, x-size, y-size, x+size, y+size ) -- Apply force to bodies in the area
```