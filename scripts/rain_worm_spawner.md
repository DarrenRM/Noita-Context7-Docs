---
title: Rain Worm Spawner
category: scripts
---

# Rain Worm Spawner

This script is responsible for spawning a small number of Rain Worms at a random location near the player.

## Core Functionality

*   **Entity Spawning:** Loads and places one or more Rain Worm entities into the game world.
*   **Randomization:** Utilizes random number generation to determine the number of worms and their types.
*   **Positioning:** Spawns worms at a random offset from the player's current position.
*   **Screen Shake:** Triggers a screen shake effect upon spawning.

## Key Attributes

### Spawn Logic

*   **`count`**: Determines the number of worms to spawn. It's randomly set between 1 and 2.
*   **`types`**: A table containing the possible Rain Worm entity types to spawn:
    *   `"worm"`
    *   `"worm_big"`
    *   `"worm_tiny"`
*   **Offset Calculation**:
    *   A `while` loop ensures the spawned worm is at least 140 units away from the player's current position (sum of absolute X and Y offsets).
    *   `off_x` and `off_y` are randomly generated within a range of -256 to 256.

### Entity Loading

*   **`EntityLoad( "data/entities/animals/" .. entity .. ".xml", pos_x + off_x, pos_y - off_y )`**: This function loads the specified Rain Worm entity XML file at the calculated world coordinates.

### Visual Effects

*   **`GameScreenshake( 30 )`**: Applies a screen shake with an intensity of 30.

## Example Usage (Conceptual)

This script is typically triggered by an in-game event or a specific entity that acts as a spawner. When executed, it will:

1.  Get the player's current position.
2.  Decide to spawn 1 or 2 worms.
3.  For each worm, randomly pick a type (e.g., "worm", "worm_big").
4.  Calculate a random offset, ensuring it's far enough from the player.
5.  Load the chosen worm entity at the calculated position.
6.  Shake the screen.