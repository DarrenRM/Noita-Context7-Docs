---
title: Pyramid Entrance Biome Script
category: scripts
---

# Pyramid Entrance Biome Script

This script defines the behavior and content for the Pyramid Entrance biome in Noita. It registers a spawn function and handles the loading of specific pixel scenes that constitute the biome's visual and structural elements.

## Core Functionality

### `RegisterSpawnFunction`

This function is crucial for the game's biome system. It associates a specific color value (`0xffffeedd`) with the `init` function, meaning that when the game encounters a pixel of this color during world generation, it will call the `init` function to populate that area.

### `init(x, y, w, h)`

This is the primary function called when the `RegisterSpawnFunction` condition is met. It's responsible for loading the visual assets that make up the Pyramid Entrance biome.

*   **`LoadPixelScene( "data/biome_impl/pyramid/left_bottom.png", "", x, y + 512, "", true )`**: Loads the "left_bottom" pixel scene. This likely forms the foundational structure or lower parts of the entrance.
*   **`LoadPixelScene( "data/biome_impl/pyramid/entrance.png", "data/biome_impl/pyramid/entrance_visual.png", x, y, "data/biome_impl/pyramid/entrance_background.png", true )`**: Loads the main "entrance" pixel scene. This includes:
    *   `data/biome_impl/pyramid/entrance.png`: The primary structural layer.
    *   `data/biome_impl/pyramid/entrance_visual.png`: Visual elements and details.
    *   `data/biome_impl/pyramid/entrance_background.png`: The background layer for the entrance.

## Unused/Placeholder Functions

The script includes numerous function definitions that are not currently implemented or used within this specific biome script. These are likely remnants from a more general biome template or intended for future expansion.

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
*   `spawn_stash(x, y)`

These functions, if implemented, would typically be responsible for populating the biome with enemies, items, environmental props, and other interactive elements.

## Dependencies

*   `dofile_once("data/scripts/director_helpers.lua")`: Provides helper functions for game directors and biome management.
*   `dofile_once("data/scripts/biome_scripts.lua")`: Contains general functions and definitions for biome scripts.