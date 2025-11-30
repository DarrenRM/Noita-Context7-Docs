---
title: Worm Deflector Death Logic
category: scripts
---

# Worm Deflector Death Logic

This script defines the behavior when a "worm deflector" entity is destroyed. Its primary function is to display a message to nearby players indicating the deflector's demise.

## Key Functionality

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the worm deflector entity is destroyed.

*   **`damage_type_bit_field`**: (Not used in this script) Bitmask representing the type of damage.
*   **`damage_message`**: (Not used in this script) String describing the damage.
*   **`entity_thats_responsible`**: (Not used in this script) The entity that caused the destruction.
*   **`drop_items`**: (Not used in this script) Boolean indicating if items should be dropped.

## Core Logic

The script checks for nearby players and, if any are within a certain radius, triggers an important game message.

### Player Proximity Check

1.  **Find Players**: It retrieves all entities with the tag "player_unit".
2.  **Get Deflector Position**: It obtains the current position (`x`, `y`) of the deflector entity.
3.  **Iterate Through Players**: For each player found:
    *   It gets the player's position (`px`, `py`).
    *   It calculates the Manhattan distance between the player and the deflector.
    *   **Distance Threshold**: If the distance is less than `240` units, it sets `display_message` to `true` and breaks the loop.

### Displaying the Message

*   If `display_message` is `true` after checking all players, the function calls `GamePrintImportant` to display the following messages:
    *   **`$log_worm_deflector_death`**: The primary title of the important message.
    *   **`$logdesc_worm_deflector_death`**: The descriptive text for the message.

```lua
dofile( "data/scripts/game_helpers.lua" )

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local players = EntityGetWithTag( "player_unit" )
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	
	local display_message = false
	
	if ( #players > 0 ) then
		for i,player_id in ipairs(players) do
			local px, py = EntityGetTransform( player_id )
			
			local distance = math.abs( px - x ) + math.abs( py - y )
			
			if ( distance < 240 ) then
				display_message = true
				break
			end
		end
	end
	
	if display_message then
		GamePrintImportant( "$log_worm_deflector_death", "$logdesc_worm_deflector_death" )
	end
end
```