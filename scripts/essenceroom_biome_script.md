---
title: Essenceroom Biome Script
category: scripts/
---

# Essenceroom Biome Script

This script defines the behavior and entity spawning for the "Essenceroom" biome in Noita. It's a relatively simple biome focused on loading a specific pixel scene and spawning essence pickups.

## Core Functionality

### `init(x, y, w, h)`
This function is called when the biome is initialized. It's responsible for loading the visual and background elements of the Essenceroom.

*   **`LoadPixelScene(filepath_png, filepath_visual_png, x, y, filepath_background_png, boolean)`**: This is the primary function used to define the biome's appearance.
    *   `data/biome_impl/essenceroom.png`: The main pixel data for the biome.
    *   `data/biome_impl/essenceroom_visual.png`: Visual layer for the biome.
    *   `x`, `y`: Coordinates for placing the scene.
    *   `data/biome_impl/essenceroom_background_with_diamond.png`: The background image, including a diamond element.
    *   `true`: A boolean flag, likely indicating whether to use the background.

### `spawn_essence(x, y)`
This function is called to spawn essence pickups within the biome.

*   **`EntityLoad(filepath_xml, x, y)`**: Loads an entity from an XML file at the specified coordinates.
    *   `data/entities/items/pickup/essence_laser.xml`: The entity definition for the essence pickup.

## Spawn Functions (Unused/Placeholder)

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or intended for future expansion.

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
*   `spawn_orb(x, y)`

## Initialization

*   **`CHEST_LEVEL = 3`**: A constant that might influence chest generation or other biome-specific properties, though not directly used in the provided `init` or `spawn_essence` functions.
*   **`dofile_once(...)`**: These lines ensure that necessary helper scripts are loaded only once, preventing potential conflicts or redundant loading.
    *   `data/scripts/director_helpers.lua`
    *   `data/scripts/biome_scripts.lua`
    *   `data/scripts/lib/utilities.lua`
*   **`RegisterSpawnFunction(...)`**: These calls register the `init` and `spawn_essence` functions to be executed at specific points during biome generation. The hexadecimal values are likely internal identifiers or seeds.