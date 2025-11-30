---
title: End Egg Spawner
category: scripts
---

# End Egg Spawner

This script controls the spawning logic for the "boss_dragon" entity, triggered by the "end_egg" entity. It ensures the boss is spawned only once and at a location relative to the player.

## Core Functionality

*   **Boss Spawn Control:** Prevents multiple spawns of the boss dragon by using a global variable.
*   **Player Proximity Check:** Spawns the boss only if the player is within a certain distance.
*   **Randomized Spawning Position:** Places the boss dragon at a randomized horizontal offset and vertical position relative to the player.
*   **Self-Destruction:** The "end_egg" entity is destroyed after its spawning duty is complete.

## Key Attributes and Logic

### Global State Management

*   `GlobalsGetValue("boss_dragon_spawned")`: Checks if the boss dragon has already been spawned. If the value is "1", the script terminates, preventing further spawns.
*   `GlobalsSetValue("boss_dragon_spawned", "1")`: Sets the global flag to indicate that the boss dragon has now been spawned.

### Player Detection and Positioning

*   `EntityGetWithTag("player_unit")`: Retrieves all entities tagged as "player\_unit". The script targets the first player found.
*   `EntityGetTransform(players[1])`: Gets the X and Y coordinates of the player.
*   **Distance Calculation:**
    *   Calculates the squared horizontal (`delta_x`) and vertical (`delta_y`) distances between the "end\_egg" and the player.
    *   If the player is above the egg (`delta_y < 0`), the vertical distance is amplified to encourage spawning when the player is overhead.
    *   The total squared distance (`delta_x + delta_y`) is compared against a threshold (`450*450`). If the player is too far away, the script terminates.

### Boss Dragon Spawning

*   `EntityLoad("data/entities/animals/boss_dragon.xml", ppos_x, ppos_y)`: Loads and spawns the `boss_dragon.xml` entity at the calculated `ppos_x` and `ppos_y`.
*   **Randomized Offset:**
    *   `ppos_x` is offset by `512` units to the left or right of the player's X position with a 50% probability.
    *   `ppos_y` is offset upwards from the player's Y position by a random value between `128` and `512`.

### Cleanup

*   `EntityGetWithTag("end_egg")`: Finds all entities tagged as "end\_egg".
*   `EntityKill(v)`: Iterates through any found "end\_egg" entities and destroys them.
*   `EntityKill(entity_id)`: Destroys the current "end\_egg" entity that executed the script.

## Example Usage (Conceptual)

This script is typically attached to an entity defined in an XML file, likely within a biome or as a special event trigger. The "end\_egg" entity itself would be configured to run this Lua script upon its creation or activation.

```lua
-- Example of how this script might be triggered by an entity
-- This is NOT part of the provided script, but illustrates its context.

-- In an entity's XML file:
-- <Entity name="end_egg_spawner">
--   <LuaComponent script="data/scripts/buildings/end_egg.lua" />
--   <Tag name="end_egg" />
--   ... other components ...
-- </Entity>
```