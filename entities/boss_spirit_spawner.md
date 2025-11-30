---
title: Boss Spirit Spawner
category: entities
---

# Boss Spirit Spawner

This entity acts as a trigger to spawn the "Boss Spirit" (Island Spirit) when specific conditions are met.

## Core Functionality

The spawner checks for the following conditions:

1.  **Player Proximity:** A player unit must be within a 200-unit radius of the spawner.
2.  **Helpless Kills Threshold:** A global variable `HELPLESS_KILLS` must be greater than or equal to 30. This variable likely tracks the number of "helpless" enemies defeated by the player.
3.  **Island Spirit Not Spawned:** A global variable `ISLANDSPIRIT_SPAWNED` must be "0", indicating the boss has not yet been spawned in the current game session.

## Key Attributes & Logic

*   **`entity_id`**: The unique identifier for this spawner entity.
*   **`x`, `y`**: The coordinates of the spawner entity.
*   **`anger`**: Retrieves the value of the global variable `HELPLESS_KILLS`. Defaults to 1 if not found.
*   **`p`**: An array containing player units found within a 200-unit radius.
*   **Conditional Spawning**:
    *   If a player is found (`#p > 0`), the `anger` threshold is met (`anger >= 30`), and the boss hasn't spawned (`GlobalsGetValue( "ISLANDSPIRIT_SPAWNED", "0" ) == "0"`), the following actions occur:
        *   **`GlobalsSetValue( "ISLANDSPIRIT_SPAWNED", "1" )`**: Sets the global flag to indicate the boss has now been spawned.
        *   **`EntityLoad( "data/entities/animals/boss_spirit/spawn_portal.xml", x, y )`**: Loads and spawns the `spawn_portal.xml` entity at the spawner's location. This is likely the visual and functional entry point for the boss encounter.
        *   **`EntityKill( entity_id )`**: Destroys the spawner entity itself, as its purpose is now fulfilled.

## Global Variables Used

*   **`HELPLESS_KILLS`**: Tracks the number of "helpless" enemies defeated.
*   **`ISLANDSPIRIT_SPAWNED`**: A flag to prevent multiple spawns of the boss.

## Example Usage (Conceptual)

This script is designed to be placed as an entity within a Noita level. It requires the `utilities.lua` script to be loaded. The `HELPLESS_KILLS` variable would be incremented by other game mechanics when specific enemy types are defeated.