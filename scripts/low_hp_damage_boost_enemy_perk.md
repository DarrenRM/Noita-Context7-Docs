---
title: Low HP Damage Boost Enemy Perk
category: scripts
---

---

# Low HP Damage Boost Enemy Perk

This script defines a perk that increases the damage of projectiles when the shooter's health is low.

## Functionality

The `shot` function is triggered when a projectile is fired. It checks the health percentage of the shooter. If the shooter's health is 20% or less, the damage of the projectile is doubled. This doubling applies to:

*   Base damage
*   Damage by type (e.g., projectile, explosion, melee)
*   Explosion configuration values (e.g., radius, energy, damage)

## Key Attributes/Elements

*   **`shot( entity_id )`**: The main function that executes the perk's logic.
*   **`shooter_id`**: Stores the entity ID of the projectile's shooter.
*   **`hp`, `max_hp`**: Variables to store the shooter's current and maximum health.
*   **`hpercent`**: Calculated health percentage (`hp / max_hp`).
*   **`hpercent <= 0.2`**: The condition for activating the damage boost (health is 20% or less).
*   **`ProjectileComponent`**: The component of the projectile that is modified.
*   **`damage`**: The base damage of the projectile.
*   **`damage_by_type`**: A table containing damage multipliers for various damage types.
*   **`config_explosion`**: A table containing configuration values for explosions.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

function shot( entity_id )
	-- Get shooter's ID
	local shooter_id = 0
	local hp,max_hp = 0,0

	-- Edit ProjectileComponent to find the shooter
	edit_component( entity_id, "ProjectileComponent", function(comp,vars)
		shooter_id = ComponentGetValue2( comp, "mWhoShot" )
	end)

	-- Check if shooter exists
	if ( shooter_id ~= nil ) and ( shooter_id ~= NULL_ENTITY ) then
		-- Get shooter's health
		edit_component( shooter_id, "DamageModelComponent", function(comp,vars)
			hp = ComponentGetValue2( comp, "hp" )
			max_hp = ComponentGetValue2( comp, "max_hp" )
		end)

		-- Check if health values are valid and shooter has health
		if ( hp ~= nil ) and ( max_hp ~= nil ) and ( hp > 0 ) and ( max_hp > 0 ) then
			local hpercent = hp / max_hp

			-- Check if health is low (<= 20%)
			if ( hpercent <= 0.2 ) then
				-- Get projectile components
				local comps = EntityGetComponent( entity_id, "ProjectileComponent" )

				if( comps ~= nil ) then
					for i,comp in ipairs(comps) do
						-- Double base damage
						local damage = ComponentGetValue2( comp, "damage" )
						damage = damage * 2.0
						ComponentSetValue2( comp, "damage", damage )

						-- Double damage by type
						local dtypes = { "projectile", "explosion", "melee", "ice", "slice", "electricity", "radioactive", "drill", "fire" }
						for a,b in ipairs(dtypes) do
							local v = tonumber(ComponentObjectGetValue( comp, "damage_by_type", b ))
							v = v * 2.0
							ComponentObjectSetValue( comp, "damage_by_type", b, tostring(v) )
						end

						-- Double explosion configuration values
						local etypes = { "explosion_radius", "ray_energy", "damage" }
						for a,b in ipairs(etypes) do
							local v = tonumber(ComponentObjectGetValue( comp, "config_explosion", b ))
							v = v * 2.0
							ComponentObjectSetValue( comp, "config_explosion", b, tostring(v) )
						end
					end
				end
			end
		end
	end
end