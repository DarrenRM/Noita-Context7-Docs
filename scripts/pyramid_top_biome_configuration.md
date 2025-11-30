---
title: Pyramid Top Biome Configuration
category: scripts/
---

# Pyramid Top Biome Configuration

This document outlines the configuration for the "Pyramid Top" biome in Noita, focusing on its entity spawning and scene loading logic.

## Core Biome Functions

The `pyramid_top.lua` script defines the behavior for the Pyramid Top biome. It registers specific functions to be called during different stages of biome initialization and loading.

### Initialization and Loading

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: This registers the `init` function to be called when the biome is first initialized.
*   **`RegisterSpawnFunction( 0xfff21df0, "load_building_stash" )`**: This registers the `load_building_stash` function, likely for loading pre-defined building elements.

### `init( x, y, w, h )`

This function is responsible for loading the visual and structural components of the Pyramid Top biome.

*   **`LoadPixelScene( "data/biome_impl/pyramid/right_bottom.png", "", x+512-61, y + 512, "", true )`**: Loads the bottom-right section of the pyramid's structure.
*   **`LoadPixelScene( "data/biome_impl/pyramid/left_bottom.png", "", x, y + 512, "", true )`**: Loads the bottom-left section of the pyramid's structure.
*   **`LoadPixelScene( "data/biome_impl/pyramid/top.png", "data/biome_impl/pyramid/top_visual.png", x, y, "data/biome_impl/pyramid/top_background.png", true )`**: Loads the main top section of the pyramid, including its visual and background elements.

### `load_building_stash( x, y )`

This function is currently empty, suggesting that any building stash logic might be handled elsewhere or is not implemented for this specific biome.

## Entity Spawning Functions

The script declares several functions for spawning various entities within the biome. While most are defined as empty stubs, `spawn_orb` demonstrates specific entity loading.

### `spawn_orb(x, y)`

This function is called to spawn specific items and entities related to orbs and sun elements.

*   **`EntityLoad( "data/entities/items/orbs/orb_01.xml", x, y )`**: Spawns a generic orb.
*   **`EntityLoad( "data/entities/items/books/book_01.xml", x+24, y )`**: Spawns a book entity near the orb.
*   **`EntityLoad( "data/entities/buildings/sun/spot_1.xml", x+24, y )`**: Spawns a sun-related building element near the orb.

### Other Declared Spawn Functions (Currently Empty)

The following functions are declared but have no implementation in this script, indicating they are either placeholders or their logic is managed by other systems:

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `spawn_chest( x, y )`
*   `spawn_blood( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_save( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_persistent_teleport( x, y )`
*   `spawn_candles( x, y )`