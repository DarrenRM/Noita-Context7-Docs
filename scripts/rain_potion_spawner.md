---
title: Rain Potion Spawner
category: scripts
---

# Rain Potion Spawner

This script handles the spawning of various potion types when a "rain potion" effect is triggered. It aims to find suitable locations near the player to drop these potions.

## Key Functionality

*   **Random Potion Selection:** Randomly selects between "potion", "potion_aggressive", and "potion_secret" types.
*   **Location Finding:** Attempts to find valid spawn points that are not too close to the player and are not obstructed by walls.
*   **Multiple Spawns:** Can spawn multiple potions in a single activation.
*   **Visual Feedback:** Triggers a screenshake upon completion.

## Core Attributes

### Potion Types

The script can spawn the following potion entities:

| Type              | Description                               |
| :---------------- | :---------------------------------------- |
| `potion`          | Standard potion item.                     |
| `potion_aggressive` | An aggressive variant of the potion.      |
| `potion_secret`   | A secret or special potion type.          |

### Spawning Logic

*   **`count`**: Determines the number of potions to spawn (randomly between 1 and 2).
*   **`raycasts`**: Used to check for wall obstructions. A higher number increases the thoroughness of the check.
*   **`dir`**: Calculates the angular separation for raycasts.
*   **`length`**: The distance each raycast extends.
*   **`limit`**: A safety counter to prevent infinite loops if a suitable spawn location cannot be found.
*   **`off_x`, `off_y`**: Randomly generated offsets from the player's position to find a spawn point.
*   **`wall`**: A boolean flag indicating if a raycast hit a surface.
*   **`failed`**: A boolean flag indicating if the spawn attempt failed after multiple tries.

### Visual Effects

*   **`GameScreenshake( 5 )`**: Triggers a screenshake with an intensity of 5.

## Example Usage (Conceptual)

This script is typically triggered by an in-game event or entity that represents a "rain potion" effect. When activated, it will:

1.  Determine how many potions to spawn.
2.  For each potion:
    *   Randomly select a potion type.
    *   Attempt to find a valid spawn location by:
        *   Generating random offsets.
        *   Performing raycasts to ensure the area is clear of walls.
        *   Retrying if the initial location is unsuitable or blocked.
    *   If a valid location is found, it spawns the selected potion entity and an accompanying "empty circle" visual.
3.  Apply a screenshake to the player.

```lua
-- Example of how the script might be called (not part of the script itself)
-- This is a conceptual representation of an event that might trigger this script.

-- Assume 'trigger_entity_id' is the ID of the entity that initiates the rain potion effect.
-- The game engine would then execute the 'rain_potion.lua' script.

-- Inside the game engine:
-- if entity_type == "rain_potion_trigger" then
--     dofile_once("data/scripts/streaming_integration/scripts/rain_potion.lua")
-- end
```