---
title: Gas Pipe Spawner
category: scripts
---

# Gas Pipe Spawner

This script is responsible for dynamically spawning `gas_pipe.xml` entities within the game world. It's designed to place these pipes in a suitable location, typically above the player's current position.

## Core Functionality

The primary goal of this script is to:
1.  **Detect a suitable spawning location:** It performs a raytrace upwards from the entity's current position to find the highest platform.
2.  **Spawn the gas pipe:** If a platform is found, it instantiates a `gas_pipe.xml` entity slightly above that platform.
3.  **Self-destruct:** The spawner entity is then removed from the game.

## Key Attributes and Logic

*   **`entity_id`**: The unique identifier for the spawner entity itself.
*   **`pos_x`, `pos_y`**: The current world coordinates of the spawner entity.
*   **`search_dist_y`**: Defines the vertical distance (downwards) the script will search for platforms. A value of `200` means it searches 200 units below the spawner.
*   **`scatter_x`**: Determines the horizontal spread for the raytracing. The script checks platforms within a range of `pos_x - scatter_x` to `pos_x + scatter_x`.
*   **`RaytracePlatforms(x, pos_y, x, pos_y - search_dist_y)`**: This is the core function for detecting platforms. It casts a ray downwards from a given `x` coordinate and `pos_y` to find the first platform it hits.
*   **`ceiling_found`**: A boolean flag indicating whether a platform was successfully detected within the search area.
*   **`ceiling_x`, `ceiling_y`**: Stores the world coordinates of the highest detected platform.
*   **`min_y`**: Keeps track of the lowest `y` coordinate (highest point) of a detected platform.
*   **`EntityLoad("data/entities/buildings/biome_modifiers/gas_pipe.xml", ceiling_x, ceiling_y + 4)`**: This function loads and spawns the `gas_pipe.xml` entity. It's placed at `ceiling_x` and `ceiling_y + 4` to position it slightly above the detected ceiling.
*   **`EntityKill(entity_id)`**: Removes the spawner entity from the game after its task is complete.

## Conditional Spawning

The script includes a crucial check:
```lua
if not DoesWorldExistAt( pos_x, pos_y - search_dist_y, pos_x, pos_y ) then return end
```
This ensures that the script only proceeds if there is a valid world segment to search within. If the spawner is too close to the edge of the loaded world, it will exit early to prevent errors.

## Summary

This script acts as a simple procedural spawner. It leverages raycasting to find a suitable "ceiling" and then places a `gas_pipe` entity there, ensuring that these pipes appear in logical locations within the game environment.