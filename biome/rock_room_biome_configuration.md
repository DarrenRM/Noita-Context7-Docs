---
title: Rock Room Biome Configuration
category: biome
---

---

# Rock Room Biome Configuration

This document outlines the configuration for the "Rock Room" biome in Noita, focusing on its entity spawning and visual setup.

## Core Biome Properties

*   **`CHEST_LEVEL`**: `3` - Indicates the general tier or difficulty level associated with chests found in this biome.

## Initialization and Spawning

The biome utilizes several `RegisterSpawnFunction` calls to define its behavior during game generation.

### Primary Initialization (`init`)

This function is responsible for loading the visual and structural elements of the Rock Room.

*   **`LoadPixelScene`**: This is the key function for defining the biome's appearance.
    *   `data/biome_impl/essenceroom.png`: The primary pixel data defining the room's layout and solid objects.
    *   `data/biome_impl/essenceroom_visual.png`: The visual layer, likely containing decorative elements and lighting.
    *   `data/biome_impl/essenceroom_background_diamond.png`: A background element, suggesting a diamond-shaped pattern or motif.

### Essence Spawning (`spawn_essence`)

This function handles the placement of specific items when the "essence" event is triggered.

*   **`EntityLoad`**: Used to place predefined entities within the biome.
    *   `data/entities/items/pickup/musicstone.xml`: Places a "musicstone" pickup item.
    *   `data/entities/items/books/book_moon.xml`: Places a "moon" book item.

## Unused/Placeholder Functions

The following functions are defined but currently empty, indicating they are either placeholders for future development or not utilized in the current implementation of the Rock Room.

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
*   `spawn_orb( x, y )`