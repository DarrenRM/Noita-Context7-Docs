---
title: Song Room Biome Script
category: scripts/
---

# Song Room Biome Script

This script defines the behavior and content for the "Song Room" biome in Noita. It focuses on loading a specific pixel scene and spawning a chest with a book.

## Core Functionality

### `init(x, y, w, h)`
This function is called when the biome is initialized. It loads the visual and gameplay elements of the Song Room.

*   **`LoadPixelScene(filepath_png, filepath_png_visual, x, y, tag, is_new_level)`**:
    *   `filepath_png`: `"data/biome_impl/alchemist_secret_music.png"` - The primary image file defining the biome's layout and elements.
    *   `filepath_png_visual`: `"data/biome_impl/alchemist_secret_music_visual.png"` - A secondary image file for visual effects or overlays.
    *   `x`, `y`: Coordinates for loading the scene.
    *   `tag`: An empty string `""` indicating no specific tag.
    *   `is_new_level`: `true` signifies this is a new level or section.

### `spawn_secret(x, y)`
This function is responsible for spawning specific entities within the Song Room.

*   **`EntityLoad(filepath_xml, x, y)`**:
    *   Loads `data/entities/buildings/chest_light.xml` at the provided `x`, `y` coordinates. This likely spawns a light-emitting chest.
    *   Loads `data/entities/items/books/book_essences.xml` at `x + 24`, `y - 16`. This spawns a specific book item, likely related to essences.

## Unused/Placeholder Functions

The following functions are defined but contain empty bodies (`end`), indicating they are not currently used or are placeholders for future implementation within this specific biome script.

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

## Constants

*   `CHEST_LEVEL = 3`: This constant likely influences the type or quality of items found in chests within this biome, though its direct usage within this script is not explicit.

## Dependencies

*   `dofile_once("data/scripts/director_helpers.lua")`
*   `dofile_once("data/scripts/biome_scripts.lua")`
*   `dofile_once("data/scripts/lib/utilities.lua")`