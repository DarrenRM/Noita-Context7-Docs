---
title: Ghost Secret Biome Configuration
category: biome
---

---

# Ghost Secret Biome Configuration

This document outlines the configuration for the "Ghost Secret" biome in Noita, focusing on its script-based generation and entity spawning.

## Core Biome Properties

*   **`CHEST_LEVEL`**: `3` - Indicates the general rarity or tier of chests found within this biome.

## Initialization and Scene Loading

The `init` function is responsible for setting up the visual and structural elements of the biome.

*   **`init(x, y, w, h)`**:
    *   Loads the primary pixel scene for the biome using `LoadPixelScene`.
    *   **`data/biome_impl/secret_lab.png`**: The main visual layer of the biome.
    *   **`data/biome_impl/secret_lab_visual.png`**: Additional visual details.
    *   **`data/biome_impl/secret_lab_background.png`**: The background layer.
    *   The `true` argument likely indicates that this scene should be loaded as a permanent part of the biome.

## Entity Spawning Functions

The following functions are defined but not directly called within the provided `init` function. They represent potential spawning logic that could be integrated into the biome's generation system.

### Placeholder Spawn Functions

These functions are defined but currently empty, serving as placeholders for future implementation.

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

### Specific Spawn Function: `spawn_orb`

This function handles the spawning of specific entities related to a "ghost orb" or similar mechanic.

*   **`spawn_orb(x, y)`**:
    *   **`EntityLoad("data/entities/animals/boss_ghost/ghost_spawn_check.xml", x, y)`**: Loads an entity likely related to checking for or spawning a ghost boss.
    *   **`EntityLoad("data/entities/buildings/hpcrystal.xml", x - 64, y)`**: Spawns an HP crystal to the left of the spawn point.
    *   **`EntityLoad("data/entities/buildings/hpcrystal.xml", x + 64, y)`**: Spawns an HP crystal to the right of the spawn point.
    *   **`EntityLoad("data/entities/buildings/snowcrystal.xml", x, y)`**: Spawns a snow crystal at the spawn point.
    *   Commented-out lines suggest potential for spawning books or music energy entities, which are currently inactive.

## Dependencies

*   `dofile_once("data/scripts/director_helpers.lua")`
*   `dofile_once("data/scripts/biome_scripts.lua")`
*   `dofile_once("data/scripts/lib/utilities.lua")`

These lines ensure that necessary helper functions and libraries are loaded before the biome script executes.