---
title: Temple Altar Left Empty Biome Configuration
category: scripts
---

---

# Temple Altar Left Empty Biome Configuration

This document details the configuration for the `temple_altar_left_empty.lua` script, which defines elements and behaviors for a specific biome in Noita. This script acts as a blueprint for generating parts of the game world, including visual elements, props, and potential enemy spawns.

## Core Functionality

The script primarily relies on `dofile_once` to include essential helper functions and shared biome logic. It then registers various spawn functions that are triggered by specific game events or conditions.

### Included Scripts

*   `data/scripts/director_helpers.lua`: Provides general utility functions for managing game directors and spawns.
*   `data/scripts/biome_scripts.lua`: Contains functions specific to biome generation and management.
*   `data/scripts/items/generate_shop_item.lua`: Handles the logic for generating shop items.
*   `data/scripts/biomes/temple_shared.lua`: Includes shared configurations and functions for Temple biomes.

## Registered Spawn Functions

These functions are registered to be called at specific points during gameplay, often tied to entity IDs or biome generation phases.

| Function Name        | Trigger ID | Description                                    |
| :------------------- | :--------- | :--------------------------------------------- |
| `init`               | `0xffffeedd` | Initializes the biome's core elements.         |
| `spawn_hp`           | `0xff6d934c` | Handles HP-related spawns (currently empty).   |
| `spawn_shopitem`     | `0xff33934c` | Spawns shop items.                             |
| `spawn_cheap_shopitem` | `0xff33935F` | Spawns cheaper shop items.                     |
| `spawn_workshop`     | `0xff10822d` | Spawns workshop-related entities.              |
| `spawn_workshop_extra` | `0xff5a822d` | Spawns additional workshop entities.           |
| `spawn_motordoor`    | `0xffFAABBA` | Spawns motor doors.                            |
| `spawn_pressureplate`| `0xffFAABBB` | Spawns pressure plates.                        |
| `spawn_music_trigger`| `0xffFF5A0A` | Spawns music triggers.                         |
| `spawn_duplicator`   | `0xff667e0a` | Spawns duplicator entities.                    |
| `spawn_areachecks`   | `0xff03DEAD` | Handles area checks (currently empty).         |
| `spawn_rubble`       | `0xffc128ff` | Spawns rubble props.                           |
| `spawn_lamp_long`    | `0xffa7a707` | Spawns long temple lamps.                      |
| `spawn_vines`        | `0xff80FF5A` | Spawns vine entities.                          |
| `spawn_statue`       | `0xff9f2a00` | Spawns temple statues.                         |

## Entity Spawn Tables

These tables define the probabilities and entities to be spawned for various biome elements.

### `g_lamp`

Defines the possible temple lamps to spawn.

| Prob | Min Count | Max Count | Entity                                     |
| :--- | :-------- | :-------- | :----------------------------------------- |
| 1.0  | 1         | 1         | "" (No lamp)                               |
| 1.0  | 1         | 1         | `data/entities/props/physics/temple_lantern.xml` |

### `g_fish`

Defines the possible fish entities to spawn.

| Prob | Min Count | Max Count | Entity                               |
| :--- | :-------- | :-------- | :----------------------------------- |
| 1.0  | 1         | 4         | `data/entities/animals/fish.xml`     |
| 1.0  | 1         | 1         | "" (No fish)                         |

### `g_rubble`

Defines the various rubble props that can spawn.

| Prob | Min Count | Max Count | Entity                                         |
| :--- | :-------- | :-------- | :--------------------------------------------- |
| 2.0  | 1         | 1         | "" (No rubble)                                 |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_01.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_02.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_03.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_04.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_05.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_06.xml` |

### `g_vines`

Defines the different types of vine entities that can spawn.

| Prob | Min Count | Max Count | Entity                                                    |
| :--- | :-------- | :-------- | :-------------------------------------------------------- |
| 0.5  | 1         | 1         | "" (No vines)                                             |
| 0.4  | 1         | 1         | `data/entities/verlet_chains/vines/verlet_vine.xml`       |
| 0.3  | 1         | 1         | `data/entities/verlet_chains/vines/verlet_vine_long.xml`  |
| 0.2  | 1         | 1         | `data/entities/verlet_chains/vines/verlet_vine_short.xml` |
| 0.2  | 1         | 1         | `data/entities/verlet_chains/vines/verlet_vine_shorter.xml` |

## Key Functions

### `init(x, y, w, h)`

This is the primary initialization function for the biome. It calls `temple_random` for biome-specific randomization and loads background and foreground pixel scenes to construct the visual environment of the altar.

*   **Loads Background:** `LoadBackgroundSprite("data/biome_impl/temple/wall_background.png", x, y - 30, 35)`
*   **Loads Altar Top:** `LoadPixelScene( "data/biome_impl/temple/altar_top.png", "", x, y-40, "", true )`
*   **Loads Altar Left:** `LoadPixelScene( "data/biome_impl/temple/altar_left.png", "data/biome_impl/temple/altar_left_visual.png", x, y-40+300, "data/biome_impl/temple/altar_left_background.png", true )`

### `spawn_lamp(x, y)`

Spawns a temple lamp using the `g_lamp` table.

### `spawn_lamp_long(x, y)`

Spawns a longer version of the temple lamp using the `g_lamp` table.

### `spawn_rubble(x, y)`

Spawns rubble props based on the probabilities defined in the `g_rubble` table.

### `spawn_vines(x, y)`

Spawns vine entities using the `g_vines` table.

### `spawn_statue(x, y)`

Loads a temple statue entity: `EntityLoad( "data/entities/props/temple_statue_01.xml", x , y )`.

### `spawn_fish(x, y)`

Spawns fish entities. The number of fish spawned is determined by the player's total orb count (`GameGetOrbCountAllTime()`).

## Unused/Empty Functions

Several functions are registered but currently have no implementation or are commented out, indicating they are either placeholders or not actively used in this specific biome configuration.

*   `spawn_hp`
*   `spawn_shopitem`
*   `spawn_cheap_shopitem`
*   `spawn_workshop`
*   `spawn_workshop_extra`
*   `spawn_motordoor`
*   `spawn_pressureplate`
*   `spawn_music_trigger` (commented out entity load)
*   `spawn_duplicator` (commented out entity load)
*   `spawn_areachecks`
*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`