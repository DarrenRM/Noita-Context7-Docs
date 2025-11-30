---
title: Fast Projectiles Perk
category: scripts
---

---

# Fast Projectiles Perk

This perk modifies projectile components to increase their speed.

## Functionality

The `shot` function is triggered when the perk is applied. It iterates through all `ProjectileComponent`s attached to the entity and multiplies their `speed_max` and `speed_min` values by 1.75.

### Key Attributes Modified

*   **`speed_max`**: The maximum speed of the projectile.
*   **`speed_min`**: The minimum speed of the projectile.

### Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

function shot( entity_id )
	local comps = EntityGetComponent( entity_id, "ProjectileComponent" )
	if( comps ~= nil ) then
		for i,comp in ipairs(comps) do
			local v = ComponentGetValue2( comp, "speed_max" )
			v = v * 1.75
			ComponentSetValue2( comp, "speed_max", v )
			
			v = ComponentGetValue2( comp, "speed_min" )
			v = v * 1.75
			ComponentSetValue2( comp, "speed_min", v )
		end
	end
end
```