---
title: Coalmine Debug Spawner
category: scripts/debug
---

# Coalmine Debug Spawner

This script provides a debugging tool to spawn all items found in the Coalmine biome at the mouse cursor's location.

## Functionality

*   **Spawns Coalmine Items:** Utilizes `DEBUG_spawn_all` to place all items defined within the `g_items` table (presumably loaded from `data/scripts/biomes/coalmine.lua`) into the game world.
*   **Mouse Cursor Placement:** Items are spawned at the precise world coordinates of the player's mouse cursor.
*   **Quantity:** Spawns a fixed quantity of 20 of each item.

## Key Elements

### `dofile("data/scripts/biomes/coalmine.lua")`

*   **Purpose:** Loads the necessary data for the Coalmine biome, which includes the definitions of items available in that biome. This is a prerequisite for spawning those items.

### `local mouse_x, mouse_y = DEBUG_GetMouseWorld()`

*   **Purpose:** Retrieves the current world coordinates of the mouse cursor. This information is used to determine the spawn location for the items.

### `DEBUG_spawn_all( g_items, mouse_x, mouse_y, 20 )`

*   **Purpose:** The core function that executes the item spawning.
    *   `g_items`: A table containing the definitions of items to be spawned. This table is populated by the `dofile` call.
    *   `mouse_x`, `mouse_y`: The world coordinates where the items will be spawned.
    *   `20`: The number of each item to spawn.

## Usage

This script is intended for debugging purposes only. To use it, you would typically execute it within a Noita modding environment that allows for debug commands.