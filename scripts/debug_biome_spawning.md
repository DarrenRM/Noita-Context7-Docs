---
title: Debug Biome Spawning
category: scripts
---

# Debug Biome Spawning

This script provides functions for debugging and spawning entities within biomes in Noita. It's primarily used for development and testing purposes.

## Core Functionality

### `RegisterSpawnFunction( a, b )`

This function is a placeholder and does not currently implement any logic. It's likely intended for future expansion or was part of an older system.

### `dofile("data/scripts/biomes/coalmine.lua")`

This line executes the `coalmine.lua` script, which registers the "coalmine" biome. This makes the coalmine biome and its associated entities and properties available for use.

### `DEBUG_spawn_all( g_items, mouse_x, mouse_y, 20 )`

This is the primary debugging function for spawning entities.

*   **`g_items`**: A global table containing various items and entities that can be spawned.
*   **`mouse_x`, `mouse_y`**: The world coordinates where the entities will be spawned, typically derived from the mouse cursor's position.
*   **`20`**: A parameter likely representing the number of entities to spawn.

This function is called to populate the game world with a specified number of entities from the `g_items` table at the given coordinates.