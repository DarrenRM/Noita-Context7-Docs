---
title: Full HP Heart (Temple) Item Script
category: scripts
---

---

# Full HP Heart (Temple) Item Script

This script defines the behavior of the "Full HP Heart" item found in temples. When picked up, it fully heals the player, increases their maximum HP, and triggers a visual effect.

## Key Attributes & Behavior

*   **Healing:** Fully restores the player's current HP to their maximum HP.
*   **Max HP Increase:** Permanently increases the player's maximum HP by a small amount (0.4).
*   **Visual Effects:** Spawns particle effects (`heart_fullhp_effect.xml` and `heart_out.xml`) at the item's location.
*   **Log Message:** Displays an important game message indicating the HP increase and healing amount.
*   **Item Removal:** The item entity is destroyed after being picked up.

## Lua Script Breakdown

```lua
dofile( "data/scripts/game_helpers.lua" )

function item_pickup( entity_item, entity_who_picked, name )

	local max_hp = 0
	local max_hp_addition = 0.4 -- The amount added to max_hp
	local healing = 0
	
	local x, y = EntityGetTransform( entity_item ) -- Get item's position

	local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )
	if( damagemodels ~= nil ) then
		for i,damagemodel in ipairs(damagemodels) do
			-- Get current max HP, max HP cap, and current HP
			max_hp = tonumber( ComponentGetValue( damagemodel, "max_hp" ) )
			local max_hp_cap = tonumber( ComponentGetValue( damagemodel, "max_hp_cap" ) )
			local hp = tonumber( ComponentGetValue( damagemodel, "hp" ) )
			
			-- Increase max HP
			max_hp = max_hp + max_hp_addition
			
			-- Adjust max HP cap if it exists and is lower than the new max HP
			if ( max_hp_cap > 0 ) then
				max_hp_cap = math.max( max_hp, max_hp_cap )
			end
			
			-- Calculate healing amount needed to reach full HP
			healing = max_hp - hp
			
			-- Set the updated values for the DamageModelComponent
			ComponentSetValue( damagemodel, "max_hp_cap", max_hp_cap)
			ComponentSetValue( damagemodel, "max_hp", max_hp)
			ComponentSetValue( damagemodel, "hp", max_hp) -- Set current HP to the new max HP
		end
	end

	-- Load particle effects
	EntityLoad("data/entities/particles/image_emitters/heart_fullhp_effect.xml", x, y-12)
	EntityLoad("data/entities/particles/heart_out.xml", x, y-8)
	
	-- Display important game message to the player
	GamePrintImportant( "$log_heart_fullhp_temple", GameTextGet( "$logdesc_heart_fullhp_temple", tostring(math.floor(max_hp_addition * 25)), tostring(math.floor(max_hp * 25)), tostring(math.floor(healing * 25)) ) )
	
	-- Remove the item from the game world
	EntityKill( entity_item )
end
```

## Related Files

*   `data/entities/particles/image_emitters/heart_fullhp_effect.xml`
*   `data/entities/particles/heart_out.xml`
*   `data/scripts/game_helpers.lua`