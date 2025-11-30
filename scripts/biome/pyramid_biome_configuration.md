---
title: Pyramid Biome Configuration
category: scripts/biome
---

# Pyramid Biome Configuration

This document details the configuration for the Pyramid biome in Noita, focusing on entity spawning and biome generation elements.

## Biome Initialization and Spawn Functions

The `pyramid.lua` script registers several functions to be called at specific points during biome generation, triggered by pixel colors in the world.

### Key Spawn Functions

| Color (RGBA) | Function Name             | Description                                     |
| :----------- | :------------------------ | :---------------------------------------------- |
| `0xffffeedd` | `init`                    | General biome initialization.                   |
| `0xff808000` | `spawn_statues`           | Spawns statues within the biome.                |
| `0xff00AC64` | `load_pixel_scene4`       | Loads a specific pixel scene configuration.     |
| `0xffC8C800` | `spawn_lamp2`             | Spawns a specific type of lamp.                 |
| `0xff400080` | `spawn_large_enemies`     | Spawns larger, more challenging enemies.        |
| `0xffC8001A` | `spawn_ghost_crystal`     | Spawns a ghost crystal entity.                  |
| `0xff82FF5A` | `spawn_crawlers`          | Placeholder for crawler spawning (currently empty). |
| `0xff647D7D` | `spawn_pressureplates`    | Spawns pressure plates.                         |
| `0xff649B7D` | `spawn_doors`             | Spawns doors.                                   |
| `0xffA07864` | `spawn_scavengers`        | Spawns scavenger enemies.                       |
| `0xff00AC33` | `load_pixel_scene3`       | Loads another specific pixel scene configuration. |
| `0xffFFCD2A` | `spawn_scorpions`         | Spawns scorpion enemies.                        |
| `0xff905ecb` | `spawn_reward_wands`      | Spawns reward wands.                            |
| `0xff905ecc` | `spawn_boss_limbs_trigger`| Spawns a trigger for boss limbs and a book.     |

## Entity Spawn Tables

These tables define the probability and types of entities that can spawn within the Pyramid biome. Each entry includes `prob` (probability), `min_count`, and `max_count`.

### `g_small_enemies`

Defines the pool of smaller enemies that can spawn.

| Prob  | Min Count | Max Count | Entity                                    | NG+ Level |
| :---- | :-------- | :-------- | :---------------------------------------- | :-------- |
| 2.5   | 0         | 0         | "" (Represents air/no spawn)              | -         |
| 0.3   | 1         | 1         | `data/entities/animals/skullrat.xml`      | -         |
| 0.2   | 1         | 1         | `data/entities/animals/skullfly.xml`      | -         |
| 0.1   | 1         | 1         | `data/entities/animals/acidshooter.xml`   | -         |
| 0.3   | 1         | 1         | `data/entities/animals/scorpion.xml`      | -         |
| 0.2   | 1         | 1         | `data/entities/animals/alchemist.xml`     | -         |
| 0.005 | 1         | 1         | `data/entities/animals/thundermage_big.xml`| -         |
| 0.1   | 1         | 1         | `data/entities/animals/wizard_neutral.xml`| -         |
| 0.1   | 1         | 2         | `data/entities/animals/thunderskull.xml`  | -         |
| 0.1   | 1         | 2         | `data/entities/animals/wizard_twitchy.xml`| -         |
| 0.05  | 1         | 2         | `data/entities/animals/wizard_hearty.xml` | -         |
| 0.05  | 1         | 2         | `data/entities/animals/wizard_weaken.xml` | -         |
| 0.05  | 1         | 2         | `data/entities/animals/ethereal_being.xml`| -         |
| 0.05  | 1         | 1         | `data/entities/buildings/hpcrystal.xml`   | 1         |
| 0.05  | 1         | 1         | `data/entities/animals/confusespirit.xml` | -         |
| 0.05  | 1         | 1         | `data/entities/animals/berserkspirit.xml` | -         |
| 0.01  | 1         | 1         | `data/entities/animals/weakspirit.xml`    | -         |

### `g_stash`

Defines items that can appear in stashes.

| Prob  | Min Count | Max Count | Entity                               |
| :---- | :-------- | :-------- | :----------------------------------- |
| 0.4   | 1         | 1         | "" (Represents no item)              |
| 0.6   | 1         | 1         | `data/entities/items/pickup/heart.xml` |

### `g_reward_items`

Defines the wands that can be obtained as rewards.

| Prob | Min Count | Max Count | Entity                           |
| :--- | :-------- | :-------- | :------------------------------- |
| 0    | 0         | 0         | "" (Represents no item)          |
| 5    | 1         | 1         | `data/entities/items/wand_level_03.xml` |
| 3    | 1         | 1         | `data/entities/items/wand_unshuffle_01.xml` |
| 1    | 1         | 1         | `data/entities/items/wand_unshuffle_02.xml` |

### `g_big_enemies`

Defines the pool of larger enemies that can spawn.

| Prob  | Min Count | Max Count | Entity                                |
| :---- | :-------- | :-------- | :------------------------------------ |
| 2.5   | 0         | 0         | "" (Represents air/no spawn)          |
| 0.1   | 1         | 1         | `data/entities/animals/acidshooter.xml` |
| 0.07  | 1         | 1         | `data/entities/animals/phantom_a.xml` |
| 0.2   | 1         | 1         | `data/entities/animals/skullfly.xml`  |
| 0.3   | 1         | 1         | `data/entities/animals/skullrat.xml`  |
| 0.07  | 1         | 1         | `data/entities/animals/phantom_b.xml` |
| 0.3   | 1         | 1         | `data/entities/animals/scorpion.xml`  |

### `g_statues`

Defines the statues that can spawn.

| Prob | Min Count | Max Count | Entity                         |
| :--- | :-------- | :-------- | :----------------------------- |
| 1.0  | 1         | 1         | `data/entities/props/statue.xml` |

### `g_scorpions`

Specific configuration for scorpion spawns.

| Prob  | Min Count | Max Count | Entity                         |
| :---- | :-------- | :-------- | :----------------------------- |
| 0.2   | 1         | 1         | "" (Represents no spawn)       |
| 0.3   | 1         | 1         | `data/entities/animals/scorpion.xml` |

### `g_pixel_scene_02` and `g_pixel_scene_04`

These tables define configurations for loading specific pixel scenes, likely used for structural elements or transitions.

| Prob | Material File                               | Visual File | Background File | Is Unique |
| :--- | :------------------------------------------ | :---------- | :-------------- | :-------- |
| 0.5  | `data/biome_impl/crypt/stairs_right.png`    | ""          | ""              | 0         |
| 0.5  | `data/biome_impl/crypt/stairs_left.png`     | ""          | ""              | 0         |

### `g_lamp` and `g_lamp2`

Define different types of lamps that can be spawned.

| Prob  | Min Count | Max Count | Entity                                       |
| :---- | :-------- | :-------- | :------------------------------------------- |
| 0.3   | 1         | 1         | "" (Represents no lamp)                      |
| 0.7   | 1         | 1         | `data/entities/props/physics_torch_stand_blue.xml` |
| 0.1   | 1         | 1         | `data/entities/props/physics_skull_01.xml`   |
| 0.1   | 1         | 1         | `data/entities/props/physics_skull_02.xml`   |
| 0.1   | 1         | 1         | `data/entities/props/physics_skull_03.xml`   |
| 0.0   | 1         | 1         | "" (Represents no lamp)                      |
| 1.0   | 1         | 1         | `data/entities/props/physics/chain_torch_blue.xml` |

### `g_save`

Configuration for save points.

| Prob  | Min Count | Max Count | Offset Y | Entity                               |
| :---- | :-------- | :-------- | :------- | :----------------------------------- |
| 0.5   | 0         | 0         | 0        | "" (Represents no save point)        |
| 0.8   | 1         | 1         | -4       | `data/entities/buildings/save_point.xml` |

### `g_props`

Defines various props that can spawn in the biome.

| Prob  | Min Count | Max Count | Offset Y | Entity                               |
| :---- | :-------- | :-------- | :------- | :----------------------------------- |
| 0.2   | 0         | 0         | 0        | "" (Represents no prop)              |
| 0.5   | 1         | 1         | -4       | `data/entities/props/physics_vase.xml` |
| 0.3   | 1         | 1         | -4       | `data/entities/props/physics_vase_longleg.xml` |
| 0.1   | 1         | 1         | 0        | `data/entities/props/physics_skull_01.xml` |
| 0.1   | 1         | 1         | 0        | `data/entities/props/physics_skull_02.xml` |
| 0.1   | 1         | 1         | 0        | `data/entities/props/physics_skull_03.xml` |

### `g_unique_enemy` and `g_large_enemies`

These tables define specific unique or large enemies.

| Prob  | Min Count | Max Count | Offset X | Entity                                  |
| :---- | :-------- | :-------- | :------- | :-------------------------------------- |
| 0.1   | 0         | 0         | 0        | "" (Represents air/no spawn)            |
| 1.0   | 1         | 1         | 2        | `data/entities/buildings/arrowtrap_right.xml` |
| 1.0   | 1         | 1         | 1        | `data/entities/buildings/arrowtrap_left.xml`  |

### `g_ghost_crystal`

Configuration for ghost crystal spawns.

| Prob | Min Count | Max Count | Entity |
| :--- | :-------- | :-------- | :----- |
| 1.0  | 0         | 0         | ""     |

### `g_pressureplates`

Defines pressure plates.

| Prob | Min Count | Max Count | Entity                           |
| :--- | :-------- | :-------- | :------------------------------- |
| 1.0  | 1         | 1         | `data/entities/props/pressure_plate.xml` |

### `g_doors`

Defines doors.

| Prob | Min Count | Max Count | Entity                             |
| :--- | :-------- | :-------- | :--------------------------------- |
| 1.0  | 1         | 1         | `data/entities/props/physics_templedoor.xml` |

### `g_candles`

Defines various types of candles.

| Prob | Min Count | Max Count | Entity                           |
| :--- | :-------- | :-------- | :------------------------------- |
| 0.33 | 1         | 1         | `data/entities/props/physics_candle_1.xml` |
| 0.33 | 1         | 1         | `data/entities/props/physics_candle_2.xml` |
| 0.33 | 1         | 1         | `data/entities/props/physics_candle_3.xml` |

### `g_pixel_scene_01` and `g_pixel_scene_03`

Define configurations for loading pixel scenes, potentially for different biome sections.

| Prob | Material File                               | Visual File                           | Background File | Is Unique |
| :--- | :------------------------------------------ | :------------------------------------ | :-------------- | :-------- |
| 1.0  | `data/biome_impl/crypt/cathedral.png`       | ""                                    | ""              | 0         |
| 1.0  | `data/biome_impl/crypt/mining.png`          | ""                                    | ""              | 0         |
| 1.0  | `data/biome_impl/crypt/lavaroom.png`        | `data/biome_impl/crypt/lavaroom_visual.png` | ""              | 0         |
| 1.0  | `data/biome_impl/crypt/pit.png`             | `data/biome_impl/crypt/pit_visual.png`    | ""              | 0         |
| 1.0  | `data/biome_impl/crypt/symbolroom.png`      | ""                                    | ""              | 0         |

### `g_scavengers`

Defines the types and probabilities of scavenger enemies.

| Prob  | Min Count | Max Count | Entities