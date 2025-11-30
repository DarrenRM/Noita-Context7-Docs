---
title: Null Room Biome Script
category: scripts
---

# Null Room Biome Script

This script defines the behavior and content of the "Null Room" biome in Noita. It focuses on loading the visual and structural elements of the room and registering specific spawn points for its unique entities.

## Core Functionality

The script primarily uses `RegisterSpawnFunction` to hook into different stages of biome generation. The `init` function is crucial for loading the visual assets and the primary hitbox for the null room.

### Key Functions

*   **`init(x, y, w, h)`**:
    *   Loads the pixel scene for the null room's visual appearance (`data/biome_impl/null_room.png`).
    *   Loads a secondary visual layer (`data/biome_impl/null_room_visual.png`).
    *   Loads the main polygonal hitbox for the null room structure.

*   **`spawn_check1(x, y)`**, **`spawn_check2(x, y)`**, **`spawn_check3(x, y)`**:
    *   These functions are registered to specific spawn IDs and are responsible for loading distinct entity configurations (`check1.xml`, `check2.xml`, `check3.xml`) within the null room. These likely represent different interactive elements or environmental features.

## Spawn Functions

The script registers several spawn functions, though many are defined as empty stubs. This suggests that the primary content loading is handled by `init` and the `spawn_check` functions, with other potential spawn types being reserved or handled elsewhere.

### Registered Spawn Functions

| Spawn ID   | Function Name   | Description                                                              |
| :--------- | :-------------- | :----------------------------------------------------------------------- |
| `0xffffeedd` | `init`          | Initializes the null room, loading its visuals and primary hitbox.       |
| `0xffbbcc00` | `spawn_check1`  | Loads the `check1.xml` entity configuration.                             |
| `0xffbbcc01` | `spawn_check2`  | Loads the `check2.xml` entity configuration.                             |
| `0xffbbcc02` | `spawn_check3`  | Loads the `check3.xml` entity configuration.                             |

### Unused/Stubbed Spawn Functions

The following functions are defined but do not contain any implementation, indicating they are not actively used by this script for spawning content:

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

## Dependencies

This script relies on several utility and helper files:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`

## Entity Loading

The script explicitly loads the following entities:

*   `data/entities/buildings/null_room/poly_hitbox.xml`
*   `data/entities/buildings/null_room/check1.xml`
*   `data/entities/buildings/null_room/check2.xml`
*   `data/entities/buildings/null_room/check3.xml`