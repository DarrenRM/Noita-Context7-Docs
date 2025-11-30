---
title: Sun Controls Script
category: scripts
---

# Sun Controls Script

This script defines the behavior of the "sun" entity, primarily its interaction with projectiles and other entities within its vicinity. It manipulates velocities and applies forces to achieve its effects.

## Key Functionality

### Projectile Interaction

The script scans for nearby entities tagged as "projectile".

*   **Targeting:** It specifically targets the first projectile found that *does not* have the "projectile_lightning" tag.
*   **Velocity Transfer:** If a suitable projectile is found and has a non-zero velocity, a portion of that velocity (0.25x) is applied as a force to the "sun" entity.
*   **Projectile Destruction:** All targeted projectiles are destroyed.

### Moon Energy Interaction

The script also scans for entities tagged as "moon\_energy" within a larger radius.

*   **Light Component Check:** It checks if the "moon\_energy" entity has a "LightComponent".
*   **Force Application:** If a "LightComponent" is present, a force is applied to the "sun" entity directed away from the "moon\_energy" entity. The magnitude of this force is fixed at 240 units.

### Self-Velocity Dampening

The "sun" entity's own velocity is dampened over time.

*   **Dampening Factor:** The current velocity is multiplied by 0.95 in each update, causing it to gradually decrease.

### Pixel Sprite Removal

The script removes any "pixelsprite" entities within a small radius (10 units) around the "sun" entity.

## Code Structure

The script utilizes standard Noita Lua functions for entity manipulation and physics.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Scan for projectiles
local targets = EntityGetInRadiusWithTag( x, y, 100, "projectile" )
-- Scan for moon energy
local targets2 = EntityGetInRadiusWithTag( x, y, 400, "moon_energy" )

local vel_x,vel_y = 0,0

-- Process projectiles
for i,v in ipairs( targets ) do
	if ( i == 1 ) and ( EntityHasTag( v, "projectile_lightning" ) == false ) then
		edit_component( v, "VelocityComponent", function(comp,vars)
			vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")
		end)
		
		if ( vel_x ~= 0 ) or ( vel_y ~= 0 ) then
			PhysicsApplyForce( entity_id, vel_x * 0.25, vel_y * 0.25 )
		end
	end
	
	EntityKill( v )
end

-- Process moon energy
for i,v in ipairs( targets2 ) do
	local tx,ty = EntityGetTransform( v )
	local test = EntityGetFirstComponent( v, "LightComponent" )
	
	if ( test ~= nil ) then
		local dir = 0 - math.atan2( ty - y, tx - x )
		
		vel_x = math.cos( dir ) * 240
		vel_y = 0 - math.sin( dir ) * 240
		
		PhysicsApplyForce( entity_id, vel_x, vel_y )
	end
end

-- Dampen self-velocity
edit_component( entity_id, "VelocityComponent", function(comp,vars)
	vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")
	
	vel_x = vel_x * 0.95
	vel_y = vel_y * 0.95
	
	ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y )
end)

-- Remove nearby pixel sprites
local props = EntityGetInRadiusWithTag( x, y, 10, "pixelsprite" )
for i,v in ipairs( props ) do
	EntityKill( v )
end
```