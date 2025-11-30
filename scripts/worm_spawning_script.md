---
title: Worm Spawning Script
category: scripts/
---

# Worm Spawning Script

This script handles the dynamic spawning of various types of worms in the game. It determines the number and type of worms to spawn based on random chance and places them near the player's current location.

## Key Functionality

*   **Randomized Spawning:** The script uses random number generation to decide how many worms will spawn and which specific worm types will be created.
*   **Worm Types:** Supports spawning of "worm", "worm_big", and "worm_tiny" entities.
*   **Placement:** Worms are spawned slightly below the player's current position, with a horizontal offset to distribute them.
*   **Visual Feedback:** Triggers a screen shake effect upon spawning to indicate the event.

## Script Logic

The script performs the following steps:

1.  **Initialization:**
    *   Retrieves the current entity's ID and its world coordinates (`pos_x`, `pos_y`).
    *   Sets a random seed based on game frame number and entity position for more varied spawns.

2.  **Determine Spawn Count:**
    *   Generates a random number between 1 and 3 to decide the quantity of worms to spawn.

3.  **Define Worm Types:**
    *   An array `types` holds the names of the different worm entities that can be spawned:
        ```lua
        local types = { "worm", "worm_big", "worm_tiny" }
        ```

4.  **Spawn Loop:**
    *   Iterates `count` times (based on the determined spawn quantity).
    *   In each iteration:
        *   A random worm type is selected from the `types` array.
        *   If a valid worm type is selected, the `EntityLoad` function is called to create the entity.
        *   The worm is spawned at `pos_x + Random(-360, 360)` (horizontal offset) and `pos_y - 300` (below the player).

5.  **Screen Shake:**
    *   After all worms are spawned, `GameScreenshake(30)` is called to add a visual cue.

## Key Attributes/Elements

*   `entity_id`: The unique identifier for the entity executing the script.
*   `pos_x`, `pos_y`: The world coordinates of the entity.
*   `count`: The number of worms to spawn (randomly determined between 1 and 3).
*   `types`: A table containing the names of the worm entity XML files to be spawned.
*   `Random(min, max)`: A utility function to generate random numbers within a specified range.
*   `EntityLoad(filepath, x, y)`: Function to load and place an entity from its XML definition.
*   `GameScreenshake(intensity)`: Function to trigger a screen shake effect.

## Example Usage (Conceptual)

This script is typically attached to a "spawner" entity or triggered by game events that require worm presence. For modding purposes, you could:

*   **Modify Spawn Count:** Adjust the `Random(1,3)` range to spawn more or fewer worms.
*   **Add New Worm Types:** Include new worm entity names in the `types` table, provided corresponding XML files exist.
*   **Alter Spawn Location:** Change the `pos_x` and `pos_y` offsets in `EntityLoad` to control where worms appear relative to the player.
*   **Adjust Screen Shake:** Modify the `intensity` value in `GameScreenshake` for a stronger or weaker visual effect.