---
title: Town Biome Spawning Configuration
category: scripts
---

---

# Town Biome Spawning Configuration

This document details the spawning configurations for entities within the Town biome in Noita, as defined by `town.lua`. It outlines the various entities that can spawn, their probabilities, and the functions responsible for their placement.

## Core Spawning Logic

The script utilizes `RegisterSpawnFunction` to associate specific entity spawn types with unique color codes. These functions are called by the game's director system when it encounters these color codes in the biome's pixel data.

### Registered Spawn Functions

| Color Code | Function Name     | Description                               |
| :--------- | :---------------- | :---------------------------------------- |
| `0xffffeedd` | `init`            | General initialization function.            |
| `0xffFF3CFF` | `spawn_chair`     | Spawns chairs.                            |
| `0xffFF1EFF` | `spawn_table`     | Spawns tables.                            |
| `0xffFF1E80` | `spawn_bottle`    | Spawns bottles.                           |
| `0xff46B428` | `spawn_shopkeeper`| Spawns shopkeepers.                       |

## Entity Spawn Tables

These tables define the probability and count for various entities that can be spawned in the Town biome. The `total_prob` is calculated internally by the `spawn` function.

### `g_small_enemies`

This table defines the probability of spawning various weak enemy types.

| Probability | Min Count | Max Count | Entity                                     |
| :---------- | :-------- | :-------- | :----------------------------------------- |
| 0.2         | 0         | 0         | (Air - no spawn)                           |
| 0.5         | 1         | 2         | `data/entities/animals/zombie_weak.xml`    |
| 0.1         | 1         | 1         | `data/entities/animals/slimeshooter_weak.xml`|
| 0.2         | 1         | 3         | `data/entities/animals/longleg.xml`        |
| 0.25        | 1         | 2         | `data/entities/animals/miner_weak.xml`     |
| 0.1         | 1         | 1         | `data/entities/animals/shotgunner_weak.xml`|

### `g_shopkeeper`

Defines the spawn for the shopkeeper.

| Probability | Min Count | Max Count | Entity                                           |
| :---------- | :-------- | :-------- | :----------------------------------------------- |
| 1.0         | 1         | 1         | `data/entities/animals/scavenger_civilian_shopkeeper.xml` |

### `g_lamp`

Configuration for spawning lamps.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| 0.5         | 0         | 0         | (Air - no spawn)                     |
| 1.5         | 1         | 2         | `data/entities/props/physics_lantern.xml` |

### `g_props`

General props that can spawn in the environment.

| Probability | Min Count | Max Count | Offset Y | Entity                             |
| :---------- | :-------- | :-------- | :------- | :--------------------------------- |
| 0.5         | 0         | 0         | 0        | (Air - no spawn)                   |
| 0.8         | 1         | 1         | 5        | `data/entities/props/physics_bed.xml` |
| 0.1         | 1         | 1         | 0        | `data/entities/props/physics_crate.xml` |

### `g_props2`

Additional props, specifically banners.

| Probability | Min Count | Max Count | Offset Y | Entity                         |
| :---------- | :-------- | :-------- | :------- | :----------------------------- |
| 1.0         | 1         | 1         | 5        | `data/entities/props/banner.xml` |

### `g_chair`

Defines the types and probabilities of chairs that can spawn.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| 0.3         | 1         | 1         | (No spawn)                           |
| 1.0         | 1         | 1         | `data/entities/props/physics_chair_1.xml` |
| 1.0         | 1         | 1         | `data/entities/props/physics_chair_2.xml` |

### `g_table`

Configuration for table spawns.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| 0.1         | 1         | 1         | (No spawn)                           |
| 1.0         | 1         | 1         | `data/entities/props/physics_table.xml` |

### `g_bottle`

Defines the spawn probabilities for different colored bottles.

| Probability | Min Count | Max Count | Offset Y | Entity                                  |
| :---------- | :-------- | :-------- | :------- | :-------------------------------------- |
| 0.1         | 0         | 0         | 0        | (Air - no spawn)                        |
| 0.3         | 1         | 1         | -5       | `data/entities/props/physics_bottle_green.xml` |
| 0.3         | 1         | 1         | -5       | `data/entities/props/physics_bottle_red.xml`   |
| 0.3         | 1         | 1         | -5       | `data/entities/props/physics_bottle_blue.xml`  |
| 0.2         | 1         | 1         | -5       | `data/entities/props/physics_bottle_yellow.xml`|

### `g_chest`

Configuration for chest spawns.

| Probability | Min Count | Max Count | Entity                         |
| :---------- | :-------- | :-------- | :----------------------------- |
| 0.6         | 0         | 0         | (Air - no spawn)               |
| 0.2         | 1         | 1         | `data/entities/items/chest.xml` |

## Helper Functions

These functions are wrappers around the generic `spawn` function, making it easier to call specific entity spawn configurations.

*   `spawn_small_enemies(x, y)`: Spawns small enemies based on `g_small_enemies`.
*   `spawn_lamp(x, y)`: Spawns a lamp with an offset.
*   `spawn_props(x, y)`: Spawns general props based on `g_props`.
*   `spawn_props2(x, y)`: Spawns banners based on `g_props2`.
*   `spawn_chair(x, y)`: Spawns chairs based on `g_chair`.
*   `spawn_table(x, y)`: Spawns tables based on `g_table`.
*   `spawn_bottle(x, y)`: Spawns bottles based on `g_bottle`.
*   `spawn_chest(x, y)`: Currently has no implementation (returns immediately).
*   `spawn_shopkeeper(x, y)`: Currently has no implementation.

## Unimplemented/Placeholder Functions

The following functions are defined but have no active spawning logic in this script. They are likely intended for future implementation or are handled by other scripts.

*   `spawn_big_enemies(x, y)`
*   `spawn_items(x, y)`
*   `spawn_props3(x, y)`
*   `spawn_blood(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_save(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_persistent_teleport(x, y)`
*   `spawn_candles(x, y)`
*   `init(x, y)`