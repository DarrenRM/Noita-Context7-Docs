---
title: Alchemist Secret Biome Script
category: scripts
---

# Alchemist Secret Biome Script

This script defines the behavior and content for the "Alchemist Secret" biome in Noita. It handles the loading of the biome's visual elements and the spawning of specific entities within it.

## Core Functionality

### Initialization (`init`)

This function is called when the biome is first loaded. It's responsible for setting up the visual representation of the Alchemist Secret area.

*   **`LoadPixelScene( "data/biome_impl/alchemist_secret.png", "data/biome_impl/alchemist_secret_visual.png", x, y, "", true )`**: This is the primary function call.
    *   It loads the biome's geometry and visual data from the specified PNG files.
    *   `x`, `y`: The coordinates where the biome is placed.
    *   `""`: An empty string for additional parameters (not used here).
    *   `true`: Indicates that this is a visual scene to be loaded.

### Spawning (`spawn_secret`)

This function is triggered to populate the Alchemist Secret biome with specific entities.

*   **`EntityLoad( "data/entities/buildings/chest_dark.xml", x, y )`**: Spawns a dark chest at the biome's origin (`x`, `y`).
*   **`EntityLoad( "data/entities/items/books/book_diamond.xml", x - 24, y - 16 )`**: Spawns a "book\_diamond" item slightly offset from the biome's origin.

## Registered Spawn Functions

The script registers specific functions to be called at certain points during gameplay or biome generation.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Associates the `init` function with a specific internal identifier (`0xffffeedd`), likely related to biome initialization.
*   **`RegisterSpawnFunction( 0xff31d0b4, "spawn_secret" )`**: Associates the `spawn_secret` function with another internal identifier (`0xff31d0b4`), likely related to entity spawning within the biome.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or remnants from a more general biome script template.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`
*   `spawn_wands( x, y )`
*   `spawn_orb(x, y)`