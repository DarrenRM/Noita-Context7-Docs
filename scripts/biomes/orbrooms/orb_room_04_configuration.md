---
title: Orb Room 04 Configuration
category: scripts/biomes/orbrooms
---

# Orb Room 04 Configuration

This document details the configuration for `orbroom_04.lua`, a script responsible for defining the content and spawning logic within a specific type of orb room in Noita.

## Core Functionality

The primary purpose of this script is to load the visual assets for the orb room and then spawn a specific orb along with associated items and effects.

### `init(x, y, w, h)`

This function is called when the orb room is initialized.

*   **`LoadPixelScene(...)`**: This is the key function that loads the visual representation of the orb room. It takes paths to:
    *   `data/biome_impl/orbroom.png`: The main pixel scene data.
    *   `data/biome_impl/orbroom_visual.png`: Visual overlay or details.
    *   `data/biome_impl/orbroom_background.png`: The background layer.
    *   `x`, `y`: The position where the scene is loaded.
    *   `true`: A boolean flag, likely indicating whether to use a specific loading mode.

### `spawn_orb(x, y)`

This function handles the spawning of the orb and its accompanying entities.

*   **`EntityLoad("data/entities/items/orbs/orb_04.xml", x, y)`**: Spawns the primary orb for this room.
*   **`EntityLoad("data/entities/items/books/book_04.xml", x - 30, y + 40)`**: Spawns a specific book entity near the orb.
*   **`EntityLoad("data/entities/misc/music_energy_000.xml", x, y - 10)`**: Spawns a music-related entity.
*   **`spawn_material_checker(...)`**: Two calls to this function are present, likely for creating particle effects or environmental interactions around the orb.
    *   The first call is positioned to the left of the orb (`x - 197`).
    *   The second call is positioned to the right of the orb (`x + 198`).
    *   Key parameters include:
        *   Material: `"snow"`
        *   Shared script: `"data/scripts/biomes/orbrooms/orbroom_shared.lua"`
        *   Particle emitter: `"data/particles/image_emitters/orbrooms/07_02.xml"`
        *   Target position for effects: `x`, `y - 100`
*   **`EntityLoad("data/entities/particles/gold_dust.xml", x, y)`**: Spawns gold dust particles at the orb's location.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or intended for use in other orb room variations.

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

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`
*   `data/scripts/biomes/orbrooms/orbroom_shared.lua`

## Constants

*   `CHEST_LEVEL = 3`: Indicates the chest level associated with this orb room.