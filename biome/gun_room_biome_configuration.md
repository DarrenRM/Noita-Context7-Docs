---
title: Gun Room Biome Configuration
category: biome
---

# Gun Room Biome Configuration

This document outlines the configuration for the "Gun Room" biome in Noita, focusing on its spawn functions and entity loading.

## Core Biome Configuration

The `gun_room.lua` script defines the behavior and content of the Gun Room biome.

### Global Variables

*   `CHEST_LEVEL`: Set to `3`, indicating a moderate level for chests within this biome.

### Required Libraries

The script depends on several utility and helper libraries:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`

### Spawn Functions Registration

The following spawn functions are registered to be called at specific points during gameplay:

*   `init`: Registered with the ID `0xffffeedd`. This function is responsible for the initial setup and loading of the biome's visual elements.
*   `spawn_essence`: Registered with the ID `0xff31d0b4`. This function handles the spawning of specific essence-related entities.

## Spawn Function Details

### `init(x, y, w, h)`

This function is called during the biome's initialization.

*   **Purpose**: Loads the visual and background assets for the Gun Room.
*   **Key Action**: Calls `LoadPixelScene` with specific image files to define the biome's appearance.
    *   `data/biome_impl/essenceroom.png`: The primary pixel scene for the room.
    *   `data/biome_impl/essenceroom_visual.png`: Visual layer for the room.
    *   `data/biome_impl/essenceroom_background_with_diamond.png`: Background layer with a diamond element.

### `spawn_essence(x, y)`

This function is responsible for spawning specific items when the "essence" event is triggered.

*   **Purpose**: Spawns a unique wand and a book.
*   **Key Actions**:
    *   `EntityLoad("data/entities/items/wands/experimental/experimental_wand_3.xml", x - 8, y + 12)`: Loads an experimental wand.
    *   `EntityLoad("data/entities/items/books/book_robot.xml", x + 8, y)`: Loads a robot book.

### Placeholder Spawn Functions

The following functions are defined but currently empty. They are likely intended for future expansion or were part of a more general biome template.

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