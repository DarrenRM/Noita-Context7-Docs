---
title: Extra Knockback Perk
category: scripts
---

---

# Extra Knockback Perk

This perk modifies projectile components to increase knockback force and related multipliers when a projectile hits an entity.

## Functionality

The `shot` function is triggered when a projectile hits something. It iterates through all `ProjectileComponent`s attached to the projectile and applies the following modifications:

### Knockback Force

*   **Increases `knockback_force`**: The existing `knockback_force` is increased by 0.5 and then multiplied by 2.0.
    *   Formula: `new_knockback_force = (old_knockback_force + 0.5) * 2.0`

### Hit Particle Force Multipliers

*   **Increases `ragdoll_force_multiplier`**: The existing `ragdoll_force_multiplier` is increased by 0.25 and then multiplied by 2.0.
    *   Formula: `new_ragdoll_force_multiplier = (old_ragdoll_force_multiplier + 0.25) * 2.0`
*   **Increases `hit_particle_force_multiplier`**: The existing `hit_particle_force_multiplier` is increased by 0.25 and then multiplied by 2.0.
    *   Formula: `new_hit_particle_force_multiplier = (old_hit_particle_force_multiplier + 0.25) * 2.0`

## Key Components Modified

*   `ProjectileComponent`
    *   `knockback_force`
    *   `ragdoll_force_multiplier`
    *   `hit_particle_force_multiplier`

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

function shot( entity_id )
	local comps = EntityGetComponent( entity_id, "ProjectileComponent" )
	if( comps ~= nil ) then
		for i,comp in ipairs(comps) do
			-- Modify knockback force
			local val = ComponentGetValue2( comp, "knockback_force" )
			val = (val + 0.5) * 2.0
			ComponentSetValue2( comp, "knockback_force", val )
			
			-- Modify hit particle force multipliers
			local dtypes = { "ragdoll_force_multiplier", "hit_particle_force_multiplier" }
			for a,b in ipairs(dtypes) do
				local v = ComponentGetValue2( comp, b )
				v = (v + 0.25) * 2.0
				ComponentSetValue2( comp, b, v )
			end
		end
	end
end
```