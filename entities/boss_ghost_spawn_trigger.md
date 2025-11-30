---
title: Boss Ghost Spawn Trigger
category: entities
---

# Boss Ghost Spawn Trigger

This entity acts as a trigger to spawn the `boss_ghost.xml` entity when a player is within a certain radius.

## Functionality

The script checks for the presence of any entities tagged with `"player_unit"` within a 300-unit radius of its own position. If one or more players are detected, it proceeds to:

1.  **Load `boss_ghost.xml`**: Spawns the boss ghost entity at the trigger's current location.
2.  **Kill Trigger**: Removes the trigger entity itself from the game.

## Key Attributes/Elements

*   **`entity_id`**: The unique identifier for this entity.
*   **`root_id`**: The root entity ID, used for getting the transform and for killing the entity.
*   **`x`, `y`**: The world coordinates of the trigger entity.
*   **`players`**: A table containing all entities within the radius tagged as `"player_unit"`.
*   **`EntityGetInRadiusWithTag( x, y, 300, "player_unit" )`**: The core function that detects nearby players.
*   **`EntityLoad( "data/entities/animals/boss_ghost/boss_ghost.xml", x, y )`**: Loads the boss ghost entity.
*   **`EntityKill( root_id )`**: Removes the trigger entity.

## Lua Script

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()
local root_id = EntityGetRootEntity( entity_id )
local x,y = EntityGetTransform( root_id )

local players = EntityGetInRadiusWithTag( x, y, 300, "player_unit" )

if ( #players > 0 ) then
	EntityLoad( "data/entities/animals/boss_ghost/boss_ghost.xml", x, y )
	EntityKill( root_id )
end
```