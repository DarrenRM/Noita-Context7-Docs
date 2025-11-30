---
title: Winter Biome Spawning Configuration
category: scripts/biome
---

# Winter Biome Spawning Configuration

This document details the spawning configurations for entities within the Winter biome in Noita, as defined by `winter.lua`. It outlines the probabilities and types of enemies, items, and props that can appear in this environment.

## Core Biome Functions

The script registers several functions to handle entity spawning and initialization.

### Registered Spawn Functions

| Function Name      | Description                                      |
| :----------------- | :----------------------------------------------- |
| `spawn_shopitem`   | Spawns shop items.                               |
| `spawn_treasure`   | Spawns treasure entities.                        |
| `spawn_specialshop`| Spawns special shop items.                       |
| `spawn_music_machine`| Spawns music machines.                           |
| `init`             | Initializes biome-specific elements and events.  |

## Entity Spawning Tables

These tables define the probability and types of entities that can spawn within the Winter biome. The `prob` attribute determines the likelihood of an entity appearing, and `min_count`/`max_count` define the number of entities to spawn.

### Small Enemies (`g_small_enemies`)

This table defines the smaller enemy types that can spawn.

| Probability | Min Count | Max Count | Entity Path                                  | Notes                               |
| :---------- | :-------- | :-------- | :------------------------------------------- | :---------------------------------- |
| 0.5         | 0         | 0         | ""                                           | Represents air, no spawns.          |
| 0.1         | 1         | 1         | `data/entities/animals/iceskull.xml`         |                                     |
| 0.2         | 1         | 1         | `data/entities/animals/scavenger_smg.xml`    |                                     |
| 0.2         | 1         | 1         | `data/entities/animals/scavenger_grenade.xml`|                                     |
| 0.1         | 1         | 1         | `data/entities/animals/thunderskull.xml`     |                                     |
| 0.05        | 1         | 1         | `data/entities/animals/thundermage.xml`      |                                     |
| 0.1         | 1         | 1         | `data/entities/animals/ethereal_being.xml`   |                                     |

### Big Enemies (`g_big_enemies`)

This table defines the larger enemy types that can spawn.

| Probability | Min Count | Max Count | Entity Path                                  | Notes                               |
| :---------- | :-------- | :-------- | :------------------------------------------- | :---------------------------------- |
| 0.5         | 0         | 0         | ""                                           | Represents air, no spawns.          |
| 0.2         | 1         | 1         | `data/entities/animals/icemage.xml`          |                                     |
| 0.15        | 1         | 1         | `data/entities/animals/phantom_a.xml`        |                                     |
| 0.15        | 1         | 1         | `data/entities/animals/phantom_b.xml`        |                                     |
| 0.2         | 1         | 1         | `data/entities/animals/tank.xml`             |                                     |
| 0.05        | 1         | 1         | `data/entities/animals/thundermage_big.xml`  |                                     |
| 0.3         | 1         | 1         | `data/entities/buildings/snowcrystal.xml`  |                                     |
| 0.05        | 1         | 1         | `data/entities/buildings/hpcrystal.xml`      |                                     |
| 0.2         | 1         | 1         | `data/entities/animals/ethereal_being.xml`   |                                     |
| 0.2         | 1         | 1         | `data/entities/buildings/ghost_crystal.xml`  |                                     |
| 0.01        | 1         | 1         | `data/entities/animals/weakspirit.xml`       | Appears only at NG+ level 2 or higher |

### Items (`g_items`)

This table is currently empty and does not define any item spawns.

### Unique Enemies (`g_unique_enemy`)

This table defines unique enemy types that can spawn.

| Probability | Min Count | Max Count | Entity Path                               |
| :---------- | :-------- | :-------- | :---------------------------------------- |
| 0.0         | 0         | 0         | ""                                        |
| 0.5         | 1         | 3         | `data/entities/animals/slimeshooter.xml`  |
| 0.3         | 1         | 2         | `data/entities/animals/acidshooter.xml`   |
| 0.1         | 1         | 1         | `data/entities/animals/giantshooter.xml`  |

### Ghost Lamp (`g_ghostlamp`)

This table defines the spawning of ghostly lamps.

| Probability | Min Count | Max Count | Entity Path                                     |
| :---------- | :-------- | :-------- | :---------------------------------------------- |
| 1.0         | 1         | 1         | `data/entities/props/physics/chain_torch_ghostly.xml` |

### Stash (`g_stash`)

This table defines the contents of stashes.

| Probability | Min Count | Max Count | Entity Path                               |
| :---------- | :-------- | :-------- | :---------------------------------------- |
| 0.4         | 1         | 1         | ""                                        |
| 0.6         | 1         | 1         | `data/entities/items/pickup/heart.xml`    |

### Candles (`g_candles`)

This table defines the spawning of different types of candles.

| Probability | Min Count | Max Count | Entity Path                           |
| :---------- | :-------- | :-------- | :------------------------------------ |
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_1.xml`|
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_2.xml`|
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_3.xml`|

### Lamp (`g_lamp`)

This table defines the spawning of mining lamps.

| Probability | Min Count | Max Count | Entity Path                           |
| :---------- | :-------- | :-------- | :------------------------------------ |
| 0.7         | 1         | 1         | `data/entities/props/physics_mining_lamp.xml` |

### Pumpkins (`g_pumpkins`)

This table defines the spawning of pumpkins, primarily for Halloween events.

| Probability | Min Count | Max Count | Entity Path                           |
| :---------- | :-------- | :-------- | :------------------------------------ |
| 5.0         | 1         | 1         | ""                                    |
| 1.0         | 1         | 1         | `data/entities/props/pumpkin_01.xml`  |
| 1.0         | 1         | 1         | `data/entities/props/pumpkin_02.xml`  |
| 1.0         | 1         | 1         | `data/entities/props/pumpkin_03.xml`  |
| 1.0         | 1         | 1         | `data/entities/props/pumpkin_04.xml`  |
| 1.0         | 1         | 1         | `data/entities/props/pumpkin_05.xml`  |

### Props (`g_props`)

This table defines the spawning of various interactive props.

| Probability | Min Count | Max Count | Offset Y | Entity Path                                     |
| :---------- | :-------- | :-------- | :------- | :---------------------------------------------- |
| 0.15        | 0         | 0         | 0        | ""                                              |
| 0.5         | 1         | 1         | 0        | `data/entities/props/physics_box_explosive.xml` |
| 0.2         | 1         | 1         | 0        | `data/entities/props/physics_propane_tank.xml`  |
| 0.3         | 1         | 1         | 0        | `data/entities/props/physics_barrel_oil.xml`    |
| 0.05        | 1         | 1         | 0        | `data/entities/props/physics_trap_electricity_enabled.xml` |

## Miscellaneous Functions

These functions are called by the game's director to manage specific spawning events.

### `init(x, y, w, h)`

This function is called during biome initialization. It handles special events like Halloween pumpkin spawns based on the current date and the biome's vertical position.

### `spawn_small_enemies(x, y)`

Spawns small enemies if the vertical position `y` is not below 0.

### `spawn_big_enemies(x, y)`

Spawns big enemies if the vertical position `y` is not below 0.

### `spawn_items(x, y)`

Currently, this function does not spawn any items.

### `spawn_unique_enemy(x, y)`

Spawns unique enemy types as defined in `g_unique_enemy`.

### `spawn_lamp(x, y)`

Spawns a mining lamp with a slight vertical offset.

### `spawn_props(x, y)`

Spawns props with a slight vertical offset.

### `spawn_potions(x, y)`

This function is a placeholder and does not spawn any potions.

### `spawn_shopitem(x, y)`

Handles the spawning of shop items, with different logic for areas above or below a certain vertical threshold.

### `spawn_specialshop(x, y)`

Handles the spawning of special shop items, similar to `spawn_shopitem`.

### `spawn_treasure(x, y)`

Loads a `towercheck.xml` entity at the specified coordinates, likely for treasure-related logic.

### `spawn_music_machine(x, y)`

Loads a music machine entity at the specified coordinates.