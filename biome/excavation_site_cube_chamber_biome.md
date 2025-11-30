---
title: Excavation Site Cube Chamber Biome
category: biome
---

# Excavation Site Cube Chamber Biome

This document details the configuration for the "Excavation Site Cube Chamber" biome in Noita, focusing on its entity spawning and visual setup.

## Core Biome Functions

The biome utilizes several registered spawn functions to populate the environment.

### Registered Spawn Functions

| ID       | Function Name   | Description                                  |
| -------- | --------------- | -------------------------------------------- |
| `0xff55AF8C` | `spawn_skulls`  | Spawns skull-related props.                  |
| `0xffffeedd` | `init`          | Initializes the biome, loading its visual assets. |
| `0xff366178` | `spawn_teleporter` | Spawns a meditation cube return teleporter.  |

## Entity Spawning Configurations

The biome defines several tables that dictate the types and probabilities of entities that can be spawned.

### `g_items`

This table defines the items that can be found within the biome, primarily focusing on wands.

| Prob | Min Count | Max Count | Entity                               |
| ---- | --------- | --------- | ------------------------------------ |
| 1    | 1         | 1         | `data/entities/items/wand_level_03.xml` |
| 1    | 1         | 1         | `data/entities/items/wand_unshuffle_02.xml` |

### `g_skulls`

This table governs the spawning of various skull and bone props.

| Prob | Min Count | Max Count | Offset Y | Entity                                 |
| ---- | --------- | --------- | -------- | -------------------------------------- |
| 6    | 1         | 1         | 0        | (Empty - likely no entity)             |
| 1.5  | 1         | 1         | 0        | `data/entities/props/physics_skull_01.xml` |
| 1.5  | 1         | 1         | 0        | `data/entities/props/physics_skull_02.xml` |
| 1.5  | 1         | 1         | 0        | `data/entities/props/physics_skull_03.xml` |
| 0.5  | 1         | 1         | 0        | `data/entities/props/physics_bone_01.xml`  |
| 0.5  | 1         | 1         | 0        | `data/entities/props/physics_bone_02.xml`  |
| 0.5  | 1         | 1         | 0        | `data/entities/props/physics_bone_03.xml`  |
| 0.5  | 1         | 1         | 0        | `data/entities/props/physics_bone_04.xml`  |
| 0.5  | 1         | 1         | 0        | `data/entities/props/physics_bone_05.xml`  |
| 0.5  | 1         | 1         | 0        | `data/entities/props/physics_bone_06.xml`  |

### `g_stones`

This table controls the spawning of stone piles and individual physics stones.

| Prob | Min Count | Max Count | Offset Y | Entity                               |
| ---- | --------- | --------- | -------- | ------------------------------------ |
| 2    | 1         | 1         | 0        | `data/entities/props/stonepile.xml`   |
| 1.5  | 1         | 1         | 0        | `data/entities/props/physics_stone_01.xml` |
| 1.5  | 1         | 1         | 0        | `data/entities/props/physics_stone_02.xml` |
| 1.5  | 1         | 1         | 0        | `data/entities/props/physics_stone_03.xml` |
| 1.5  | 1         | 1         | 0        | `data/entities/props/physics_stone_04.xml` |
| 4    | 1         | 1         | 0        | (Empty - likely no entity)             |

### `g_lamp`

This table defines the spawning of temple lanterns.

| Prob   | Min Count | Max Count | Entity                                     |
| ------ | --------- | --------- | ------------------------------------------ |
| 0.25   | 1         | 1         | (Empty - likely no entity)                 |
| 1.0    | 1         | 1         | `data/entities/props/physics/temple_lantern.xml` |

## Biome Initialization and Spawning Functions

These functions are called during gameplay to set up and populate the biome.

### `init(x, y, w, h)`

Loads the visual assets for the cube chamber biome.

*   **Pixel Scene:** `data/biome_impl/excavationsite/cube_chamber.png`
*   **Visual Scene:** `data/biome_impl/excavationsite/cube_chamber_visual.png`
*   **Background Scene:** `data/biome_impl/excavationsite/cube_chamber_background.png`

### `spawn_lamp(x, y)`

Spawns lamps using the `g_lamp` configuration.

### `spawn_skulls(x, y)`

Spawns skull and bone props using the `g_skulls` configuration.

### `spawn_teleporter(x, y)`

Loads the `teleport_meditation_cube_return.xml` entity at the specified coordinates.

### Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script, indicating they are either not used for this specific biome or are intended for future expansion.

*   `spawn_shopitem( x, y )`
*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_props(x, y)`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_items(x, y)`