---
title: Moon Room Biome Configuration
category: biome
---

# Moon Room Biome Configuration

This document details the configuration for the "Moon Room" biome in Noita, focusing on its spawning mechanics and associated entities.

## Core Biome Properties

The Moon Room is a special biome primarily designed for spawning specific items and effects.

*   **`CHEST_LEVEL`**: `3` - Indicates the general tier or rarity of chests that might appear in this biome.

## Initialization and Spawning Functions

The biome utilizes several `RegisterSpawnFunction` calls to define its behavior during gameplay.

### Primary Initialization (`init`)

This function is called when the biome is first loaded.

*   **`LoadPixelScene`**: This is the core function for defining the visual and structural layout of the Moon Room.
    *   `"data/biome_impl/essenceroom.png"`: Defines the collision and structural layer of the biome.
    *   `"data/biome_impl/essenceroom_visual.png"`: Defines the visual appearance of the biome.
    *   `x`, `y`: Coordinates for placing the biome.
    *   `"data/biome_impl/essenceroom_background_diamond.png"`: Specifies the background element for the biome.
    *   `true`: Likely indicates whether the background should be tiled or not.

### Essence Spawning (`spawn_essence`)

This function is responsible for spawning specific items and perks when the "essence" event is triggered within the biome.

*   **`perk_spawn( x - 8, y, "MOON_RADAR" )`**: Spawns the "MOON_RADAR" perk at a position slightly to the left of the center of the spawn point.
*   **`EntityLoad("data/entities/items/books/book_music_a.xml", x + 8, y )`**: Loads the "book\_music\_a.xml" entity (likely a music book) at a position slightly to the right of the center of the spawn point.

## Unused/Placeholder Functions

The following functions are defined within the script but appear to be placeholders or are not actively used in this specific biome configuration. They are listed for completeness but do not contribute to the Moon Room's current functionality.

*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `spawn_lamp`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`
*   `spawn_wands`
*   `spawn_orb`