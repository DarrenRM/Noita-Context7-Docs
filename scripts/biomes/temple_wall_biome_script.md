---
title: Temple Wall Biome Script
category: scripts/biomes
---

# Temple Wall Biome Script

This script defines the behavior and spawning logic for the "Temple Wall" biome in Noita. It primarily focuses on initializing the biome by spawning a shared altar element.

## Core Functions

The script registers an `init` function to be called when the biome is loaded.

### `init(x, y, w, h)`

*   **Purpose:** Initializes the Temple Wall biome.
*   **Parameters:**
    *   `x`: The x-coordinate of the biome's origin.
    *   `y`: The y-coordinate of the biome's origin.
    *   `w`: The width of the biome.
    *   `h`: The height of the biome.
*   **Action:** Calls `spawn_altar_top(x, y, true)` to place the shared altar structure.

## Helper Functions (Unused/Placeholder)

The following functions are declared but do not contain any implementation in this specific script. They are likely intended as placeholders or are handled by other shared biome scripts.

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_items(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `spawn_lamp(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`
*   `spawn_potions(x, y)`
*   `spawn_wands(x, y)`

## Dependencies

This script relies on several other Lua files for its functionality:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`
*   `data/scripts/biomes/temple_altar_top_shared.lua`

## Constants

*   `CHEST_LEVEL = 3`: A constant likely used for determining chest rarity or type within this biome context.