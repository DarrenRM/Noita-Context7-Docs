---
title: Workshop Temporary Check Script
category: scripts
---

---

# Workshop Temporary Check Script

This script is designed to be attached to an entity that acts as a temporary workshop or trigger. Its primary function is to check for the presence of a player within a specified radius. If no player is found, the entity is automatically destroyed.

## Key Functionality

*   **Player Proximity Check:** Detects if a "player_unit" tag exists within a 240-pixel radius of the entity.
*   **Self-Destruction:** If no player is detected within the radius, the entity running this script is removed from the game.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Includes utility functions.

local entity_id = GetUpdatedEntityID() -- Gets the unique ID of the entity this script is attached to.
local x, y = EntityGetTransform( entity_id ) -- Retrieves the entity's current X and Y coordinates.

-- Checks for entities with the "player_unit" tag within a 240-pixel radius.
local p = EntityGetInRadiusWithTag( x, y, 240, "player_unit" )

-- If the count of found player units is zero (i.e., no player is nearby)...
if ( #p == 0 ) then
	EntityKill( entity_id ) -- ...destroy the entity.
end
```

## Usage Notes

*   This script is ideal for temporary entities that should only exist while the player is nearby, such as certain workshop mechanics or interactive elements that despawn when not in use.
*   The `player_unit` tag is crucial for the script to correctly identify the player.
*   The radius of 240 pixels can be adjusted by modifying the third argument in `EntityGetInRadiusWithTag`.