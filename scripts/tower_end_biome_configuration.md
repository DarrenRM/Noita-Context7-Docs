---
title: Tower End Biome Configuration
category: scripts/
---

# Tower End Biome Configuration

This document outlines the configuration for the "Tower End" biome in Noita, focusing on its script-based spawning and initialization logic.

## Core Biome Properties

*   **CHEST_LEVEL**: `3` - Indicates the general difficulty or tier of chests found within this biome.

## Initialization and Spawning Functions

The biome utilizes several registered spawn functions to populate its environment.

### `init(x, y, w, h)`

This function is responsible for the initial setup of the biome's visual and structural elements.

*   **`LoadPixelScene`**: This is the primary function called, loading the visual and structural components of the biome.
    *   `data/biome_impl/essenceroom.png`: Defines the base pixel data for the biome.
    *   `data/biome_impl/essenceroom_visual.png`: Provides visual overlays and details.
    *   `x`, `y`: Coordinates for placement.
    *   `data/biome_impl/essenceroom_background_with_diamond.png`: Specifies a background element with a diamond motif.
    *   `true`: Likely indicates whether the background should be rendered.

### `spawn_essence(x, y)`

This function handles the spawning of specific high-tier items and structures within the biome.

*   **Wand Spawning**: Three "good" wands are spawned to provide players with powerful options.
    *   `data/entities/items/wands/wand_good/wand_good_1.xml`
    *   `data/entities/items/wands/wand_good/wand_good_2.xml`
    *   `data/entities/items/wands/wand_good/wand_good_3.xml`
    *   These are placed relative to the `x`, `y` coordinates, suggesting a horizontal spread.
*   **Teleport Back**: A `mystery_teleport_back` building is spawned, likely for player convenience or as a unique biome feature.
    *   `data/entities/buildings/mystery_teleport_back.xml`
    *   Placed below the wand spawns.

## Unused/Placeholder Functions

The following functions are defined but appear to be empty placeholders, indicating they are not currently used for this biome's specific implementation or are intended for future expansion.

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