---
title: Enemy Perk Giver
category: scripts
---

# Enemy Perk Giver

This script provides functionality to grant random perks to enemies in Noita, with specific exclusions for certain boss types.

## Core Functionality

The primary function `give_random_perk( entity_id )` is designed to be called on an enemy entity. It checks if the entity is a worm, dragon, ghost, or lukki. If it's not one of these excluded types, it proceeds to select and apply a random perk.

### Key Logic

1.  **Entity Identification:** Retrieves the `entity_id` of the enemy.
2.  **Exclusion Check:** Determines if the entity is a `WormAIComponent`, `BossDragonComponent`, `GhostComponent`, or `LimbBossComponent`. If it is any of these, the perk-giving process is skipped.
3.  **Perk Filtering:** Iterates through the `perk_list` to identify perks that are marked as `usable_by_enemies`.
4.  **Random Perk Selection:** If there are valid perks available for enemies, a random perk is chosen from the filtered list.
5.  **Perk Application:** The selected perk is then applied to the enemy entity using the `give_perk_to_enemy` function.

## Important Considerations

*   **Perk List Dependency:** This script relies on `data/scripts/perks/perk_list.lua` for its perk data.
*   **Enemy Eligibility:** Not all perks are designed to be given to enemies. The `usable_by_enemies` flag in `perk_list.lua` is crucial for determining which perks can be assigned.
*   **Boss Exclusions:** The script explicitly prevents certain powerful boss entities from receiving additional perks, likely to maintain game balance.
*   **Random Seed:** The random seed is set based on the entity's position (`x`, `y`) to ensure a degree of determinism for perk distribution in specific locations.

## Lua Functions Used

*   `dofile()`: Includes other Lua files.
*   `dofile_once()`: Includes Lua files only once.
*   `EntityGetTransform()`: Gets the position of an entity.
*   `SetRandomSeed()`: Sets the seed for the random number generator.
*   `EntityGetComponent()`: Retrieves a component from an entity.
*   `table.insert()`: Adds an element to a table.
*   `Random()`: Generates a random number within a specified range.
*   `give_perk_to_enemy()`: (Assumed to be defined elsewhere, likely in `game_helpers.lua` or a similar utility script) Applies a perk to an entity.

```lua
dofile( "data/scripts/game_helpers.lua" )
dofile_once("data/scripts/lib/utilities.lua")
dofile_once( "data/scripts/perks/perk_list.lua" )

function give_random_perk( entity_id )
	local x, y = EntityGetTransform( entity_id )
	
	SetRandomSeed( x, y )

	local worm = EntityGetComponent( entity_id, "WormAIComponent" )
	local dragon = EntityGetComponent( entity_id, "BossDragonComponent" )
	local ghost = EntityGetComponent( entity_id, "GhostComponent" )
	local lukki = EntityGetComponent( entity_id, "LimbBossComponent" )
	
	if ( worm == nil ) and ( dragon == nil ) and ( ghost == nil ) and ( lukki == nil ) then
		local valid_perks = {}
		
		for i,perk_data in ipairs( perk_list ) do
			if ( perk_data.usable_by_enemies ~= nil ) and perk_data.usable_by_enemies then
				table.insert( valid_perks, i )
			end
		end
		
		if ( #valid_perks > 0 ) then
			local rnd = Random( 1, #valid_perks )
			local result = valid_perks[rnd]
			
			local perk_data = perk_list[result]
			
			-- Assumes give_perk_to_enemy is defined elsewhere and handles the actual perk application
			give_perk_to_enemy( perk_data, entity_id, 0 )
		end
	end
end
```