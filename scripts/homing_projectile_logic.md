---
title: Homing Projectile Logic
category: scripts
---

---

# Homing Projectile Logic

This script defines the behavior for projectiles that can home in on targets. It finds nearby entities with the "homing_target" tag and attempts to steer the projectile towards the closest valid target.

## Key Attributes and Logic

### Target Acquisition

*   **`radius`**: The search radius for potential targets. (Default: `32`)
*   **`targets`**: A list of entities within the specified `radius` that possess the "homing_target" tag.

### Target Validation

The script iterates through acquired `targets` and applies the following checks:

*   **`v ~= target`**: Ensures the projectile does not target its own shooter.
*   **`GameGetGameEffect( v, "CHARM" ) == 0`**: Excludes charmed entities from being targeted.
*   **`EntityGetHerdRelation( target, v ) < 60`**: Prioritizes targets that are not part of the shooter's herd (or have a low herd relation value).

### Homing Mechanism

*   If a valid target is found, the projectile's transform is updated to match the target's hitbox center.
*   **`EntityApplyTransform( root_id, tx, ty )`**: This function applies the updated transform, causing the projectile to change direction.
*   The loop breaks after the first valid target is found and locked onto.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local root_id = EntityGetRootEntity( entity_id )
local x, y = EntityGetTransform( entity_id )
local radius = 32
local targets = EntityGetInRadiusWithTag( x, y, radius, "homing_target" )
local comp = EntityGetFirstComponent( root_id, "ProjectileComponent" )

if ( comp ~= nil ) then
	local target = ComponentGetValue2( comp, "mWhoShot" )
	
	for i,v in ipairs( targets ) do
		if ( v ~= target ) and ( GameGetGameEffect( v, "CHARM" ) == 0 ) and ( EntityGetHerdRelation( target, v ) < 60 ) then
			local tx, ty = EntityGetFirstHitboxCenter( v )
			
			EntitySetTransform( root_id, tx, ty )
			EntityApplyTransform( root_id, tx, ty )
			break
		end
	end
end
```