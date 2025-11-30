---
title: Lake Biome Configuration
category: scripts
---

# Lake Biome Configuration

This document details the configuration for the "lake" biome in Noita, focusing on entity spawning and biome-specific functions.

## Biome Initialization and Spawn Functions

The `lake.lua` script registers several functions to be called by the game's director system based on specific color codes found in the biome's tile data.

### Registered Spawn Functions

| Color Code (Hex) | Function Name        | Description                                      |
| :--------------- | :------------------- | :----------------------------------------------- |
| `0xff667600`     | `spawn_teleport_back`| Spawns a `teleport_bunker_back` entity.          |
| `0xffb2a700`     | `spawn_bunker2`      | Spawns a `bunker2` entity.                       |
| `0xffb27600`     | `spawn_bunker`       | Spawns a `bunker` entity.                        |
| `0xff390000`     | `spawn_alchemist`    | Spawns a `failed_alchemist` entity (commented out). |
| `0xffffeedd`     | `init`               | The primary initialization function for the biome. |
| `0xFF5078C8`     | `spawn_rainbow_card` | Creates a `RAINBOW_TRAIL` item action entity.    |
| `0xff235a15`     | `spawn_music_machine`| Spawns a `music_machine_02` entity.              |

## Entity Spawning Tables

These tables define the probability and count of various entities that can spawn within the lake biome.

### `g_small_enemies`

This table defines the potential small enemies that can spawn. The current configuration primarily includes a zombie with a low probability.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| `1.5`       | `0`       | `0`       | `""` (Represents air, no spawn)      |
| `0.3`       | `1`       | `1`       | `data/entities/animals/zombie.xml`   |
| `0.05`      | `1`       | `1`       | `data/entities/animals/miner.xml`    |
| `0.025`     | `1`       | `1`       | `data/entities/animals/rat.xml`      |

### `g_items`

This table defines the potential items that can spawn. It includes a variety of weapons with varying probabilities.

| Probability | Min Count | Max Count | Entity                                     |
| :---------- | :-------- | :-------- | :----------------------------------------- |
| `1.2`       | `0`       | `0`       | `""` (Represents air, no spawn)            |
| `0.01`      | `1`       | `1`       | `data/entities/items/grenadelauncher.xml`  |
| `0.1`       | `1`       | `1`       | `data/entities/items/machinegun.xml`       |
| `0.001`     | `1`       | `1`       | `data/entities/items/opgun.xml`            |
| `0.0001`    | `1`       | `1`       | `data/entities/items/lightninggun.xml`     |
| `0.02`      | `1`       | `1`       | `data/entities/items/rocketlauncher.xml`   |
| `0.1`       | `1`       | `1`       | `data/entities/items/shotgun.xml`          |

### `g_unique_enemy`

This table defines unique or special enemies that can spawn.

| Probability | Min Count | Max Count | Entity                                   |
| :---------- | :-------- | :-------- | :--------------------------------------- |
| `0.0`       | `0`       | `0`       | `""` (Represents air, no spawn)          |
| `0.5`       | `1`       | `3`       | `data/entities/animals/slimeshooter.xml` |
| `0.3`       | `1`       | `2`       | `data/entities/animals/acidshooter.xml`  |
| `0.1`       | `1`       | `1`       | `data/entities/animals/giantshooter.xml` |

### `g_ghostlamp`

This table defines the spawning of ghostly lamps.

| Probability | Min Count | Max Count | Entity                                       |
| :---------- | :-------- | :-------- | :------------------------------------------- |
| `1.0`       | `1`       | `1`       | `data/entities/props/physics_chain_torch_ghostly.xml` |

### `g_stash`

This table defines the contents of stashes found in the biome.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| `0.4`       | `1`       | `1`       | `""` (Empty stash)                   |
| `0.6`       | `1`       | `1`       | `data/entities/items/pickup/heart.xml` |

### `g_candles`

This table defines the types of candles that can spawn.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| `0.33`      | `1`       | `1`       | `data/entities/props/physics_candle_1.xml` |
| `0.33`      | `1`       | `1`       | `data/entities/props/physics_candle_2.xml` |
| `0.33`      | `1`       | `1`       | `data/entities/props/physics_candle_3.xml` |

### `g_lamp`

This table defines the type of mining lamp that can spawn.

| Probability | Min Count | Max Count | Entity                                   |
| :---------- | :-------- | :-------- | :--------------------------------------- |
| `0.7`       | `1`       | `1`       | `data/entities/props/physics_mining_lamp.xml` |

## Core Biome Functions

These are the primary functions called by the game's director system for this biome.

### `init(x, y, w, h)`

*   **Description:** The main initialization function for the biome. It calls `parallel_check` to handle parallel processing of biome generation.
*   **Parameters:**
    *   `x`: The x-coordinate of the biome's origin.
    *   `y`: The y-coordinate of the biome's origin.
    *   `w`: The width of the biome.
    *   `h`: The height of the biome.

### `spawn_small_enemies(x, y)`

*   **Description:** Spawns small enemies based on the `g_small_enemies` table. It includes a check to prevent spawning if `y` is negative.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_big_enemies(x, y)`

*   **Description:** A placeholder function for spawning big enemies. Currently, it is commented out and does not spawn any entities.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_items(x, y)`

*   **Description:** A placeholder function for spawning items. Currently, it does nothing.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_unique_enemy(x, y)`

*   **Description:** Spawns unique enemies based on the `g_unique_enemy` table.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_lamp(x, y)`

*   **Description:** Spawns a mining lamp slightly offset from the given coordinates.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_props(x, y)`

*   **Description:** A placeholder function for spawning general props. Currently, it does nothing.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_potions(x, y)`

*   **Description:** A placeholder function for spawning potions. Currently, it does nothing.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_alchemist(x, y)`

*   **Description:** A function intended to spawn an alchemist. The entity loading is commented out.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_bunker(x, y)`

*   **Description:** Spawns a `bunker` entity at the specified coordinates.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_bunker2(x, y)`

*   **Description:** Spawns a `bunker2` entity at the specified coordinates.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_teleport_back(x, y)`

*   **Description:** Spawns a `teleport_bunker_back` entity at the specified coordinates.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_rainbow_card(x, y)`

*   **Description:** Creates a `RAINBOW_TRAIL` item action entity at the specified coordinates.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.

### `spawn_music_machine(x, y)`

*   **Description:** Spawns a `music_machine_02` entity at the specified coordinates.
*   **Parameters:**
    *   `x`: The x-coordinate for spawning.
    *   `y`: The y-coordinate for spawning.