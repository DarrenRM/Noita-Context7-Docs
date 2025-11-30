---
title: Orb Room 03 Biome Configuration
category: biome
---

---

# Orb Room 03 Biome Configuration

This document details the configuration for a specific orb room biome in Noita, focusing on its entity spawning and visual setup.

## Core Biome Settings

*   **CHEST_LEVEL**: `3` - Indicates the general difficulty or tier associated with this orb room.

## Initialization Function (`init`)

This function is responsible for loading the visual and background elements of the orb room.

*   **`init(x, y, w, h)`**:
    *   Loads the primary pixel scene for the orb room: `data/biome_impl/orbroom.png`.
    *   Loads the associated visual layer: `data/biome_impl/orbroom_visual.png`.
    *   Sets the origin coordinates for placement: `x`, `y`.
    *   Loads the background layer: `data/biome_impl/orbroom_background.png`.
    *   The `true` parameter likely enables a specific background rendering mode.

## Orb Spawning Function (`spawn_orb`)

This function defines the entities that appear when the orb room is generated, centered around the main orb.

*   **`spawn_orb(x, y)`**:
    *   **Main Orb**: `EntityLoad( "data/entities/items/orbs/orb_03.xml", x, y )` - Spawns the primary orb entity for this room.
    *   **Book**: `EntityLoad( "data/entities/items/books/book_03.xml", x - 30, y + 40 )` - Spawns a specific book entity, offset from the orb's position.
    *   **Music Energy**: `EntityLoad( "data/entities/misc/music_energy_000.xml", x, y - 10 )` - Spawns a music energy entity, slightly above the orb.
    *   **Gold Dust**: `EntityLoad( "data/entities/particles/gold_dust.xml", x, y )` - Spawns a particle effect, likely for visual flair around the orb.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this specific file. They are likely intended for future use or are part of a common biome template.

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