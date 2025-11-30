---
title: Vault Entrance Biome Configuration
category: biome
---

# Vault Entrance Biome Configuration

This document details the configuration for the Vault Entrance biome in Noita, focusing on its entity spawning and visual setup.

## Biome Initialization

The `init` function is responsible for loading the visual and structural elements of the Vault Entrance biome.

### Key Attributes:

*   **`LoadPixelScene`**: This function is called to load the biome's visual and physical layout.
    *   `"data/biome_impl/vault/entrance.png"`: Specifies the primary image file for the biome's appearance.
    *   `"data/biome_impl/vault/entrance_visual.png"`: Specifies an additional image file for visual effects or layering.
    *   `x, y-200`: Sets the position where the biome is loaded, with a slight vertical offset.
    *   `""`: An empty string for an optional biome name.
    *   `true`: Indicates that the biome should be loaded.

## Entity Spawning Tables

The following tables define the probabilities and types of entities that can spawn within the Vault Entrance biome.

### `g_small_enemies`

This table governs the spawning of smaller, common enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group (not explicitly used for spawning logic here). |
| `prob`      | The probability of a specific entity spawning.                           |
| `min_count` | The minimum number of this entity to spawn.                              |
| `max_count` | The maximum number of this entity to spawn.                              |
| `entity`    | The XML path to the entity to spawn.                                     |

| Entity Path                               | Prob  | Min Count | Max Count |
| :---------------------------------------- | :---- | :-------- | :-------- |
| `data/entities/animals/zombie.xml`        | 0.3   | 1         | 1         |
| `data/entities/animals/miner.xml`         | 0.05  | 1         | 1         |
| `data/entities/animals/rat.xml`           | 0.025 | 1         | 1         |
| *(Empty entity)*                          | 1.5   | 0         | 0         |

### `g_items`

This table defines the potential items that can be found within the biome.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group (not explicitly used for spawning logic here). |
| `prob`      | The probability of a specific item spawning.                             |
| `min_count` | The minimum number of this item to spawn.                                |
| `max_count` | The maximum number of this item to spawn.                                |
| `entity`    | The XML path to the item entity to spawn.                                |

| Entity Path                                     | Prob   | Min Count | Max Count |
| :------------------------------------------------ | :----- | :-------- | :-------- |
| `data/entities/items/grenadelauncher.xml`         | 0.01   | 1         | 1         |
| `data/entities/items/machinegun.xml`              | 0.1    | 1         | 1         |
| `data/entities/items/opgun.xml`                   | 0.001  | 1         | 1         |
| `data/entities/items/lightninggun.xml`            | 0.0001 | 1         | 1         |
| `data/entities/items/rocketlauncher.xml`          | 0.02   | 1         | 1         |
| `data/entities/items/shotgun.xml`                 | 0.1    | 1         | 1         |
| *(Empty entity)*                                  | 1.2    | 0         | 0         |

### `g_unique_enemy`

This table specifies unique or more dangerous enemy types that can spawn.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group (not explicitly used for spawning logic here). |
| `prob`      | The probability of a specific unique enemy spawning.                     |
| `min_count` | The minimum number of this enemy to spawn.                               |
| `max_count` | The maximum number of this enemy to spawn.                               |
| `entity`    | The XML path to the unique enemy entity to spawn.                        |

| Entity Path                               | Prob  | Min Count | Max Count |
| :---------------------------------------- | :---- | :-------- | :-------- |
| `data/entities/animals/slimeshooter.xml`  | 0.5   | 1         | 3         |
| `data/entities/animals/acidshooter.xml`   | 0.3   | 1         | 2         |
| `data/entities/animals/giantshooter.xml`  | 0.1   | 1         | 1         |
| *(Empty entity)*                          | 0.0   | 0         | 0         |

### `g_ghostlamp`

This table defines the spawning of ghostly lamps.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group (not explicitly used for spawning logic here). |
| `prob`      | The probability of a ghostly lamp spawning.                              |
| `min_count` | The minimum number of this lamp to spawn.                                |
| `max_count` | The maximum number of this lamp to spawn.                                |
| `entity`    | The XML path to the ghostly lamp entity to spawn.                        |

| Entity Path                                       | Prob | Min Count | Max Count |
| :------------------------------------------------ | :--- | :-------- | :-------- |
| `data/entities/props/physics_chain_torch_ghostly.xml` | 1.0  | 1         | 1         |

### `g_candles`

This table controls the spawning of various types of candles.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group (not explicitly used for spawning logic here). |
| `prob`      | The probability of a specific candle type spawning.                      |
| `min_count` | The minimum number of this candle to spawn.                              |
| `max_count` | The maximum number of this candle to spawn.                              |
| `entity`    | The XML path to the candle entity to spawn.                              |

| Entity Path                           | Prob | Min Count | Max Count |
| :------------------------------------ | :--- | :-------- | :-------- |
| `data/entities/props/physics_candle_1.xml` | 0.33 | 1         | 1         |
| `data/entities/props/physics_candle_2.xml` | 0.33 | 1         | 1         |
| `data/entities/props/physics_candle_3.xml` | 0.33 | 1         | 1         |

### `g_lamp`

This table defines the spawning of regular lamps.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group (not explicitly used for spawning logic here). |
| `prob`      | The probability of a lamp spawning.                                      |
| `min_count` | The minimum number of this lamp to spawn.                                |
| `max_count` | The maximum number of this lamp to spawn.                                |
| `entity`    | The XML path to the lamp entity to spawn.                                |

| Entity Path                               | Prob | Min Count | Max Count |
| :---------------------------------------- | :--- | :-------- | :-------- |
| `data/entities/props/physics/lantern_small.xml` | 0.7  | 1         | 1         |
| *(Empty entity)*                          | 0.4  | 1         | 1         |

## Spawn Functions

These functions are called by the game to trigger entity spawning based on the defined tables.

### `spawn_small_enemies(x, y)`

*   Spawns entities defined in the `g_small_enemies` table at the given coordinates `(x, y)`.
*   Returns `0` if `y` is less than `0` to prevent spawning below the playable area.

### `spawn_big_enemies(x, y)`

*   Spawns entities defined in the `g_big_enemies` table at the given coordinates `(x, y)`.
*   Returns `0` if `y` is less than `0`.

### `spawn_items(x, y)`

*   This function is currently defined to `return` without spawning any items.

### `spawn_unique_enemy(x, y)`

*   Spawns entities defined in the `g_unique_enemy` table at the given coordinates `(x, y)`.

### `spawn_lamp(x, y)`

*   Spawns entities defined in the `g_lamp` table at the given coordinates `(x+5, y+10)`, with a slight offset.