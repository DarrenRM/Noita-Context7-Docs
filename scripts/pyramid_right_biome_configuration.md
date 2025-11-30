---
title: Pyramid Right Biome Configuration
category: scripts
---

# Pyramid Right Biome Configuration

This document details the configuration for the "Pyramid Right" biome in Noita, focusing on its script-based generation and elements.

## Core Biome Initialization

The `init` function is the primary entry point for this biome. It's responsible for loading the visual and structural components of the Pyramid Right area.

### `init(x, y, w, h)`

*   **Purpose:** Initializes the Pyramid Right biome at the specified coordinates.
*   **Parameters:**
    *   `x`, `y`: The base coordinates for biome placement.
    *   `w`, `h`: The width and height of the biome area (often not directly used in this specific script but part of the standard signature).

### Key Loading Functions Called:

*   `LoadPixelScene("data/biome_impl/pyramid/right_bottom.png", "", x+512-61, y + 512, "", true)`: Loads a specific pixel scene for the lower portion of the right pyramid.
*   `LoadPixelScene("data/biome_impl/pyramid/right.png", "", x, y, "", true)`: Loads the main pixel scene for the Pyramid Right biome.
*   `LoadBackgroundSprite("data/biome_impl/pyramid/right_background.png", x, y, 99.9)`: Loads the background sprite for this biome.

## Spawn Functions (Unused/Placeholder)

The following functions are defined but do not contain any implementation in this specific script. They are likely placeholders or intended for use in more complex biome configurations.

### Enemy Spawning

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`

### Item and Prop Spawning

*   `spawn_items(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`

### Utility and Environmental Spawning

*   `spawn_lamp(x, y)`
*   `spawn_chest(x, y)`
*   `spawn_blood(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`

### Scene and Persistence

*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_persistent_teleport(x, y)`
*   `spawn_save(x, y)`

## Global Constants and Dependencies

*   `CHEST_LEVEL = 3`: A global constant likely influencing chest generation or difficulty.
*   `dofile_once("data/scripts/director_helpers.lua")`: Includes helper functions for biome and director logic.
*   `dofile_once("data/scripts/biome_scripts.lua")`: Includes general biome scripting utilities.
*   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Registers the `init` function to be called during biome generation, likely associated with a specific biome ID (`0xffffeedd`).