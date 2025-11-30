---
title: Drain Pipe Spawner
category: scripts
---

# Drain Pipe Spawner

This script is responsible for dynamically spawning `drain_pipe.xml` entities in the game world. It's designed to place these pipes on the ceiling above the spawner's location.

## Core Functionality

The primary goal of this script is to find a suitable ceiling position and then instantiate a `drain_pipe` entity there.

### Key Attributes and Logic

*   **`entity_id`**: Retrieves the unique identifier for the entity running this script.
*   **`pos_x`, `pos_y`**: Gets the current world coordinates of the spawner entity.
*   **`search_dist_y`**: Defines the vertical distance (downwards) to search for a ceiling.
*   **`scatter_x`**: Determines the horizontal spread for raycasting to find the ceiling.
*   **`RaytracePlatforms(x, pos_y, x, pos_y - search_dist_y)`**: This is the core raycasting function. It checks for platforms (ceilings) within the specified horizontal (`x`) and vertical (`pos_y` to `pos_y - search_dist_y`) range.
*   **Ceiling Detection**: The script iterates horizontally around the spawner's `pos_x` to find the highest reachable ceiling (`min_y`).
*   **`EntityLoad("data/entities/buildings/biome_modifiers/drain_pipe.xml", ceiling_x, ceiling_y + 4)`**: If a ceiling is found, this function loads and spawns the `drain_pipe` entity at the detected ceiling's X-coordinate and slightly above its Y-coordinate.
*   **`EntityKill(entity_id)`**: After its task is complete (either spawning a pipe or failing to find a ceiling), the spawner entity itself is removed from the game.

### Conditional Spawning

The script includes a crucial check:

*   **`if not DoesWorldExistAt( pos_x, pos_y - search_dist_y, pos_x, pos_y ) then return end`**: This ensures that the script only proceeds if there's a valid world segment within the search area. If not, it exits early to prevent errors.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions, likely including `RaytracePlatforms` and `DoesWorldExistAt`.

## Example Usage (Conceptual)

This script would typically be attached to an entity placed in a level that is intended to have drain pipes appear above it. The `drain_pipe.xml` entity itself would then contain the visual and functional aspects of the drain pipe.