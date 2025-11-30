---
title: Mountain Center Biome Spawning Configuration
category: scripts/biome
---

---

# Mountain Center Biome Spawning Configuration

This document details the spawning configurations for entities within the Mountain Center biome in Noita, as defined by `mountain_center.lua`. It outlines the probability and quantity of various entities that can appear in this biome.

## Global Spawning Variables

*   `CHEST_LEVEL`: Defines the level of action IDs spawned from chests. Currently set to `7`.

## Entity Spawn Tables

These tables define the probability and count for different types of entities that can be spawned. The `total_prob` is calculated by summing the `prob` of all entries.

### Small Enemies (`g_small_enemies`)

This table governs the spawning of smaller, common enemies.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity Path                                     | Notes                               |
| :------------------- | :---------------------- | :---------------------- | :---------------------------------------------- | :---------------------------------- |
| 1.0                  | 0                       | 0                       | ""                                              | Base probability, no spawns initially |
| 0.4                  | 1                       | 2                       | `data/entities/animals/zombie.xml`              | Zombie spawns                       |
| 0.4                  | 1                       | 2                       | `data/entities/animals/bat.xml`                 | Bat spawns                          |
| 0.2                  | 1                       | 2                       | `data/entities/animals/longleg.xml`             | Longleg spawns                      |
| 0.09                 | 1                       | 1                       | `data/entities/animals/bigbat.xml`              | Big bat spawns                      |

### Lamps (`g_lamp`)

Configuration for spawning lamps.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity Path                                     | Notes                               |
| :------------------- | :---------------------- | :---------------------- | :---------------------------------------------- | :---------------------------------- |
| 0.4                  | 1                       | 1                       | ""                                              | No lamp spawn                       |
| 0.7                  | 1                       | 1                       | `data/entities/props/physics/lantern_small.xml` | Small lantern spawns                |

### Props (`g_props`)

This table controls the spawning of various physics-based props.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Offset Y (`offset_y`) | Entity Path                                     | Notes                               |
| :------------------- | :---------------------- | :---------------------- | :-------------------- | :---------------------------------------------- | :---------------------------------- |
| 0.2                  | 0                       | 0                       | 0                     | ""                                              | No prop spawn                       |
| 0.5                  | 1                       | 1                       | 0                     | `data/entities/props/physics_box_explosive.xml` | Explosive box spawns                |
| 0.25                 | 1                       | 1                       | -3                    | `data/entities/props/physics/minecart.xml`      | Minecart spawns                     |
| 0.2                  | 1                       | 1                       | 0                     | `data/entities/props/physics_barrel_radioactive.xml` | Radioactive barrel spawns           |
| 0.07                 | 1                       | 1                       | 0                     | `data/entities/props/physics_barrel_oil.xml`    | Oil barrel spawns                   |

### Save Points (`g_save`)

Configuration for spawning save points.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Offset Y (`offset_y`) | Entity Path                               | Notes                               |
| :------------------- | :---------------------- | :---------------------- | :-------------------- | :---------------------------------------- | :---------------------------------- |
| 0.5                  | 0                       | 0                       | 0                     | ""                                        | No save point spawn                 |
| 0.5                  | 1                       | 1                       | -4                    | `data/entities/buildings/save_point.xml`  | Save point spawns                   |

### Ghost Lamps (`g_ghostlamp`)

Spawning configuration for ghost lamps.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity Path                                 | Notes                               |
| :------------------- | :---------------------- | :---------------------- | :------------------------------------------ | :---------------------------------- |
| 1.0                  | 1                       | 1                       | `data/entities/props/physics_chain_torch.xml` | Chain torch spawns                  |

### Stashes (`g_stash`)

Defines the probability of spawning items from stashes.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity Path                       | Notes                               |
| :------------------- | :---------------------- | :---------------------- | :-------------------------------- | :---------------------------------- |
| 0.4                  | 1                       | 1                       | ""                                | No item spawn                       |
| 0.6                  | 1                       | 1                       | `data/entities/items/pickup/heart.xml` | Heart pickup spawns                 |

### Candles (`g_candles`)

Configuration for spawning different types of candles.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity Path                   | Notes                               |
| :------------------- | :---------------------- | :---------------------- | :---------------------------- | :---------------------------------- |
| 0.33                 | 1                       | 1                       | `data/entities/props/candle_1.xml` | Candle type 1 spawns                |
| 0.33                 | 1                       | 1                       | `data/entities/props/candle_2.xml` | Candle type 2 spawns                |
| 0.33                 | 1                       | 1                       | `data/entities/props/candle_3.xml` | Candle type 3 spawns                |

## Biome Specific Spawn Functions

These functions are called by the game's director to spawn entities at specific locations within the biome.

### `spawn_chest(x, y)`

*   **Description:** A specialized function for spawning chests, potentially with custom logic. The current implementation is commented out and would typically call `entity_load_chest`.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_small_enemies(x, y)`

*   **Description:** Spawns small enemies based on the `g_small_enemies` table.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_big_enemies(x, y)`

*   **Description:** Placeholder function for spawning larger enemies. Currently has no implementation.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_lamp(x, y)`

*   **Description:** Spawns lamps based on the `g_lamp` table.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.
    *   `0`: Unused parameter.
    *   `0`: Unused parameter.

### `spawn_props(x, y)`

*   **Description:** Spawns props based on the `g_props` table, with a slight vertical offset.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.
    *   `-3`: Vertical offset.
    *   `0`: Unused parameter.

### `spawn_unique_enemy(x, y)`

*   **Description:** Placeholder function for spawning unique enemies. Currently has no implementation.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `load_pixel_scene(x, y)`

*   **Description:** Loads a random pixel scene from `g_pixel_scene_01`.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `load_pixel_scene2(x, y)`

*   **Description:** Loads a random pixel scene from `g_pixel_scene_02`.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_save(x, y)`

*   **Description:** Placeholder function for spawning save points. Currently has no implementation.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.