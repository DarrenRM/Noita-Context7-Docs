---
title: Greed Crystal Death Effect
category: scripts
---

# Greed Crystal Death Effect

This script defines the behavior when a "greed crystal" entity is destroyed. Its primary function is to remove any associated "greed curse" tags from players and then signal that the greed curse is no longer active.

## Core Functionality

The `death` function is the main entry point for this script. It's triggered when the entity associated with this script is killed.

### Key Actions:

*   **Player Identification:** It first identifies all entities tagged as "player_unit".
*   **Greed Curse Removal:** For each player, it iterates through their children entities. If a child entity has the "greed_curse" tag, it is destroyed (effectively removing the curse from the player).
*   **Global Flag Update:** After processing all players, it sets a global game flag `"greed_curse_gone"` to indicate that the greed curse has been removed from the game.
*   **Player Notification:** It displays an important in-game message to the player(s) indicating that the greed curse is gone.

## Function Breakdown

```lua
function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	-- Get all entities tagged as "player_unit"
	local players = EntityGetWithTag( "player_unit" )
	-- Get the ID of the entity that triggered this death event
	local entity_id = GetUpdatedEntityID()
	-- Get the transform (position) of the entity that triggered this death event
	local x, y = EntityGetTransform( entity_id )
	
	-- Check if there are any players in the game
	if ( #players > 0 ) then
		-- Loop through each player
		for i,player_id in ipairs(players) do
			-- Get all child entities of the current player
			local c = EntityGetAllChildren( player_id )
			
			-- Check if the player has any children entities
			if ( c ~= nil ) then
				-- Loop through each child entity of the player
				for a,b in ipairs( c ) do
					-- Check if the child entity has the "greed_curse" tag
					local valid = EntityHasTag( b, "greed_curse" )
					
					-- If the child entity has the "greed_curse" tag, destroy it
					if valid then
						EntityKill( b )
					end
				end
			end
		end
	end
	
	-- Set a global flag to indicate the greed curse is gone
	GameAddFlagRun( "greed_curse_gone" )
	-- Display an important message to the player(s)
	GamePrintImportant( "$log_greed_curse_away", "$logdesc_greed_curse_away" )
end
```