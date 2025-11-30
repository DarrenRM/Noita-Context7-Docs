---
title: Orb Room 10 Configuration
category: scripts/biomes/orbrooms
---

---

# Orb Room 10 Configuration

This document details the configuration for Orb Room 10, a specific biome variant within Noita. It focuses on the entities and visual elements loaded when this room is generated.

## Core Settings

*   **CHEST\_LEVEL**: `3` - Indicates the general tier or difficulty associated with chests found in this room.

## Initialization (`init` function)

The `init` function is responsible for loading the primary visual and structural components of the orb room.

*   **`LoadPixelScene`**: This is the key function for defining the room's appearance.
    *   `"data/biome_impl/orbroom.png"`: The main pixel data defining the room's layout and solid objects.
    *   `"data/biome_impl/orbroom_visual.png"`: Provides visual details and effects for the room.
    *   `"data/biome_impl/orbroom_background.png"`: Loads the background image for the room.
    *   `true`: Likely indicates that the scene should be loaded with collision data.

## Orb Spawning (`spawn_orb` function)

This function handles the placement of the main orb and associated items within the room.

### Key Entities Loaded:

| Entity Path                                       | Description                               | Offset (relative to x, y) |
| :------------------------------------------------ | :---------------------------------------- | :------------------------ |
| `data/entities/items/orbs/orb_10.xml`             | The primary orb for this room.            | `(0, 0)`                  |
| `data/entities/items/books/book_10.xml`           | A specific book item.                     | `(-30, 40)`               |
| `data/entities/misc/music_energy_000.xml`         | A music or ambient effect entity.         | `(0, -10)`                |
| `data/entities/particles/gold_dust.xml`           | Particle effect for gold dust.            | `(0, 0)`                  |

### Material Checkers:

These functions likely spawn entities that monitor specific materials and trigger particle effects.

*   **Left Side Checker**:
    *   Material: `"oil"`
    *   Particle Emitter: `"data/particles/image_emitters/orbrooms/10_01.xml"`
    *   Position: `(x - 197, y - 11)`
*   **Right Side Checker**:
    *   Material: `"radioactive_liquid"`
    *   Particle Emitter: `"data/particles/image_emitters/orbrooms/10_02.xml"`
    *   Position: `(x + 198, y - 11)`

## Unused Spawn Functions

The following functions are defined but appear to be empty or unused in this specific orb room configuration:

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