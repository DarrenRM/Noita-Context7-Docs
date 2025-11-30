---
title: Bunker Check Script
category: scripts
---

# Bunker Check Script

This script checks for the presence of a player within a certain radius and a specific game flag. If both conditions are met, it spawns various entities and then destroys the entity running the script. This is likely used to trigger the appearance of a "bunker" or special area under specific circumstances.

## Key Functionality

### Player Proximity Check
- **`EntityGetInRadiusWithTag( x, y, 200, "player_unit" )`**: Detects if any entity with the tag "player_unit" is within a 200-unit radius of the script's current position.

### Game Flag Condition
- **`GameHasFlagRun( "fishing_hut_a" )`**: Checks if the game has the flag `"fishing_hut_a"` set. This flag likely signifies a specific game state or progression.

### Entity Spawning (Conditional)
If both the player proximity and game flag conditions are true, the following entities are spawned:

- **`data/entities/props/physics_table.xml`**: A physics table is spawned slightly above the script's position.
- **`data/entities/animals/failed_alchemist.xml`**: A "failed alchemist" entity is spawned to the left of the script's position.
- **`data/entities/items/wands/experimental/experimental_wand_2.xml`**: An experimental wand is spawned to the right and slightly below the script's position.
- **`CreateItemActionEntity( "COLOUR_...", x, y )`**: A series of "color" action entities are spawned in a line to the right of the script's position. These likely represent collectible items or triggers related to colors.
    - `COLOUR_RED`
    - `COLOUR_ORANGE`
    - `COLOUR_YELLOW`
    - `COLOUR_GREEN`
    - `COLOUR_BLUE`
    - `COLOUR_PURPLE`
    - `COLOUR_RAINBOW`
    - `COLOUR_INVIS`
- **`data/entities/buildings/workshop_temporary.xml`**: A temporary workshop building is spawned near the script's position.

### Script Termination
- **`EntityKill( entity_id )`**: The entity running this script is destroyed after the spawning sequence is complete.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Check for player in radius and specific game flag
local p = EntityGetInRadiusWithTag( x, y, 200, "player_unit" )

if ( #p > 0 ) and GameHasFlagRun( "fishing_hut_a" ) then
	-- Spawn various entities if conditions are met
	EntityLoad("data/entities/props/physics_table.xml", x, y + 16)
	EntityLoad("data/entities/animals/failed_alchemist.xml", x - 24, y)
	EntityLoad("data/entities/items/wands/experimental/experimental_wand_2.xml", x + 64, y - 32)
	
	-- Spawn color action entities
	CreateItemActionEntity( "COLOUR_RED", x + 32, y - 8)
	CreateItemActionEntity( "COLOUR_ORANGE", x + 44, y - 9)
	CreateItemActionEntity( "COLOUR_YELLOW", x + 56, y - 10)
	CreateItemActionEntity( "COLOUR_GREEN", x + 68, y - 11)
	CreateItemActionEntity( "COLOUR_BLUE", x + 80, y - 12)
	CreateItemActionEntity( "COLOUR_PURPLE", x + 92, y - 13)
	CreateItemActionEntity( "COLOUR_RAINBOW", x + 104, y - 14)
	CreateItemActionEntity( "COLOUR_INVIS", x + 116, y - 15)
	
	EntityLoad("data/entities/buildings/workshop_temporary.xml", x + 48, y)
	
	-- Destroy the script entity
	EntityKill( entity_id )
end
```