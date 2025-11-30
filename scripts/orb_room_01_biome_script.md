---
title: Orb Room 01 Biome Script
category: scripts
---

# Orb Room 01 Biome Script

This script defines the behavior and content for a specific type of orb room biome in Noita. It focuses on loading the visual assets for the room and spawning a key item: the orb.

## Core Functionality

The primary function of this script is to load the visual representation of the orb room and then trigger the spawning of the orb itself and associated items.

### `init(x, y, w, h)`

This function is called when the orb room biome is initialized.

*   **`LoadPixelScene( "data/biome_impl/orbroom.png", "", x, y, "data/biome_impl/orbroom_background.png", true )`**: This is the key function call that loads the visual elements of the orb room.
    *   `"data/biome_impl/orbroom.png"`: Specifies the main pixel scene file for the room's foreground.
    *   `""`: An empty string, likely for an optional overlay.
    *   `x, y`: The coordinates where the scene will be loaded.
    *   `"data/biome_impl/orbroom_background.png"`: Specifies the background image for the room.
    *   `true`: A boolean flag, potentially indicating whether the background should be rendered.

### `spawn_orb(x, y)`

This function handles the spawning of the orb and related items within the orb room.

*   **`EntityLoad( "data/entities/items/orbs/orb_01.xml", x, y )`**: Spawns the main orb item.
*   **`EntityLoad( "data/entities/items/books/book_01.xml", x - 30, y + 40 )`**: Spawns a book item near the orb.
*   **`EntityLoad( "data/entities/misc/music_energy_000.xml", x, y - 10 )`**: Spawns a music energy entity, likely for atmospheric effects.

## Configuration

*   **`CHEST_LEVEL = 3`**: This constant likely influences the type or quality of chests that might appear in this biome, though it's not directly used in the provided `init` or `spawn_orb` functions.

## Unused Functions

The script includes numerous function definitions that are not called within the provided `init` or `spawn_orb` functions. These are likely placeholders or remnants from a more complex biome template. They include functions for spawning various types of enemies, items, props, lamps, and loading different pixel scenes.

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