---
title: Hills Biome Spawning Configuration
category: scripts/
---

# Hills Biome Spawning Configuration

This document details the spawning configurations for the "hills" biome in Noita, focusing on the entities and items that can appear within this environment. It outlines the probabilities and counts for various enemy types, items, and decorative props.

## Core Biome Functions

The `hills.lua` script registers several functions to be called by the game's director system for spawning specific elements.

### Registered Spawn Functions

| Function Name       | Description                                     |
| :------------------ | :---------------------------------------------- |
| `spawn_shopitem`    | Handles spawning of shop items.                 |
| `spawn_treasure`    | Handles spawning of treasure entities.          |
| `spawn_specialshop` | Handles spawning of special shop items.         |
| `init`              | The primary initialization function for the biome. |
| `spawn_music_machine` | Handles spawning of music machines.             |

## Entity Spawn Tables

These tables define the probability and quantity of different entities that can spawn within the biome. The `total_prob` is calculated by the game based on the individual `prob` values.

### `g_small_enemies`

Configuration for spawning smaller enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this entity spawning.                                 |
| `min_count` | The minimum number of this entity to spawn.                              |
| `max_count` | The maximum number of this entity to spawn.                              |
| `entity`    | The path to the entity's XML file. An empty string signifies no spawn. |

| `prob` | `min_count` | `max_count` | `entity`                         |
| :----- | :---------- | :---------- | :------------------------------- |
| 1.5    | 0           | 0           | ""                               |
| 0.3    | 1           | 1           | `data/entities/animals/zombie.xml` |
| 0.05   | 1           | 1           | `data/entities/animals/miner.xml`  |
| 0.025  | 1           | 1           | `data/entities/animals/rat.xml`    |

### `g_items`

Configuration for spawning general items. Currently, this table is mostly empty, with a placeholder for air.

| `prob` | `min_count` | `max_count` | `entity` |
| :----- | :---------- | :---------- | :------- |
| 1.2    | 0           | 0           | ""       |

### `g_unique_enemy`

Configuration for spawning unique or more powerful enemy types.

| `prob` | `min_count` | `max_count` | `entity`                               |
| :----- | :---------- | :---------- | :------------------------------------- |
| 0.0    | 0           | 0           | ""                                     |
| 0.5    | 1           | 3           | `data/entities/animals/slimeshooter.xml` |
| 0.3    | 1           | 2           | `data/entities/animals/acidshooter.xml`  |
| 0.1    | 1           | 1           | `data/entities/animals/giantshooter.xml` |

### `g_ghostlamp`

Configuration for spawning ghostly lamp props.

| `prob` | `min_count` | `max_count` | `entity`                                     |
| :----- | :---------- | :---------- | :------------------------------------------- |
| 1.0    | 1           | 1           | `data/entities/props/physics/chain_torch_ghostly.xml` |

### `g_stash`

Configuration for spawning stashes, which can contain items.

| `prob` | `min_count` | `max_count` | `entity`                         |
| :----- | :---------- | :---------- | :------------------------------- |
| 0.4    | 1           | 1           | ""                               |
| 0.6    | 1           | 1           | `data/entities/items/pickup/heart.xml` |

### `g_candles`

Configuration for spawning various types of candles.

| `prob` | `min_count` | `max_count` | `entity`                         |
| :----- | :---------- | :---------- | :------------------------------- |
| 0.33   | 1           | 1           | `data/entities/props/physics_candle_1.xml` |
| 0.33   | 1           | 1           | `data/entities/props/physics_candle_2.xml` |
| 0.33   | 1           | 1           | `data/entities/props/physics_candle_3.xml` |

### `g_lamp`

Configuration for spawning mining lamps.

| `prob` | `min_count` | `max_count` | `entity`                           |
| :----- | :---------- | :---------- | :--------------------------------- |
| 0.7    | 1           | 1           | `data/entities/props/physics_mining_lamp.xml` |

### `g_pumpkins`

Configuration for spawning pumpkins, with a special condition for Halloween.

| `prob` | `min_count` | `max_count` | `entity`                         |
| :----- | :---------- | :---------- | :------------------------------- |
| 5.0    | 1           | 1           | ""                               |
| 1.0    | 1           | 1           | `data/entities/props/pumpkin_01.xml` |
| 1.0    | 1           | 1           | `data/entities/props/pumpkin_02.xml` |
| 1.0    | 1           | 1           | `data/entities/props/pumpkin_03.xml` |
| 1.0    | 1           | 1           | `data/entities/props/pumpkin_04.xml` |
| 1.0    | 1           | 1           | `data/entities/props/pumpkin_05.xml` |

## Biome Initialization and Spawning Logic

The `init` function and other helper functions control how and when entities are spawned within the hills biome.

### `init(x, y, w, h)`

This function is called during biome generation. It includes a special condition for Halloween.

*   **Halloween Event:** If the current date is October 31st and the biome's vertical position (`y`) is within a specific range (`-1000` to `0`), it spawns multiple pumpkins. The spawn area is also adjusted.

### `spawn_small_enemies(x, y)`

Spawns small enemies based on the `g_small_enemies` table, provided the `y` coordinate is not below ground.

### `spawn_big_enemies(x, y)`

A placeholder function for spawning big enemies. Currently, it's commented out and does not spawn anything.

### `spawn_items(x, y)`

A placeholder function for spawning general items. Currently, it does not spawn anything.

### `spawn_unique_enemy(x, y)`

Spawns unique enemies based on the `g_unique_enemy` table.

### `spawn_lamp(x, y)`

Spawns a mining lamp slightly above the given `y` coordinate.

### `spawn_props(x, y)`

A placeholder function for spawning props. Currently, it does not spawn anything.

### `spawn_potions(x, y)`

A placeholder function for spawning potions. Currently, it does not spawn anything.

### `spawn_shopitem(x, y)`

Handles the spawning of shop items. The logic differs based on the `y` coordinate, with a chance for a special item spawn at lower depths.

### `spawn_specialshop(x, y)`

Handles the spawning of special shop items, with logic similar to `spawn_shopitem`.

### `spawn_treasure(x, y)`

Loads a `towercheck.xml` entity at the specified coordinates, likely for treasure-related mechanics.

### `spawn_music_machine(x, y)`

Loads a `music_machine_02.xml` entity at the specified coordinates.