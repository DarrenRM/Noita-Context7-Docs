---
title: Orb Room 11 Biome Configuration
category: biome
---

# Orb Room 11 Biome Configuration

This document details the configuration for a specific orb room biome in Noita, identified as `orbroom_11.lua`. It outlines the core elements and entities loaded when this biome is generated.

## Core Biome Settings

*   **`CHEST_LEVEL`**: `3` - Indicates the general difficulty or tier associated with this biome's loot.

## Initialization and Scene Loading

The `init` function is responsible for setting up the visual and structural elements of the orb room.

*   **`init(x, y, w, h)`**:
    *   Loads the primary pixel scene for the orb room using `LoadPixelScene`.
        *   `data/biome_impl/orbroom.png`: The main visual layer of the room.
        *   `data/biome_impl/orbroom_visual.png`: Additional visual details.
        *   `data/biome_impl/orbroom_background.png`: The background layer.

## Orb and Associated Entity Spawning

The `spawn_orb` function defines the specific items and entities that appear within this orb room.

*   **`spawn_orb(x, y)`**:
    *   **`orb_11.xml`**: The primary orb entity for this room.
    *   **`book_11.xml`**: A specific book entity, likely related to progression or spells.
    *   **`music_energy_000.xml`**: An entity that influences the ambient music or adds an energy effect.
    *   **`gold_dust.xml`**: A particle effect, likely for visual flair or indicating a reward.

## Unused Spawn Functions

The following spawn functions are defined but not called within this specific biome script, suggesting they are generic functions available for other biomes or modding purposes.

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