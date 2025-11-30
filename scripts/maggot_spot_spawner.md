---
title: Maggot Spot Spawner
category: scripts
---

# Maggot Spot Spawner

This script defines a spawner entity that, when a player is nearby, spawns a tiny maggot and a magical symbol particle effect, then destroys itself.

## Key Attributes

*   **`entity_id`**: The unique identifier for the spawner entity.
*   **`pos_x`, `pos_y`**: The world coordinates of the spawner entity.
*   **`t`**: A table containing entities within a 220-unit radius tagged as "player\_unit".

## Behavior

1.  **Player Proximity Check**: The script checks if any entities tagged "player\_unit" are within a 220-unit radius of the spawner.
2.  **Spawning**: If a player is detected:
    *   A `maggot_tiny.xml` entity is loaded at the spawner's position.
    *   A `magical_symbol_fast.xml` particle emitter is loaded at the spawner's position.
3.  **Self-Destruction**: After spawning the entities, the spawner entity (`entity_id`) is killed.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local t = EntityGetInRadiusWithTag( pos_x, pos_y, 220, "player_unit" )

if ( #t > 0 ) then
	local eid = EntityLoad( "data/entities/animals/maggot_tiny/maggot_tiny.xml", pos_x, pos_y )
	EntityLoad( "data/entities/particles/image_emitters/magical_symbol_fast.xml", pos_x, pos_y )

	EntityKill( entity_id )
end
```