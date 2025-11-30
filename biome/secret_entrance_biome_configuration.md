---
title: Secret Entrance Biome Configuration
category: biome
---

# Secret Entrance Biome Configuration

This document details the configuration for the "Secret Entrance" biome in Noita, focusing on its initialization and enemy spawning logic.

## Core Biome Initialization

The `init` function is responsible for loading the visual and structural elements of the secret entrance biome.

### Key Functions

*   **`init(x, y, w, h)`**: This is the primary initialization function for the biome.
    *   It loads the main biome scene using `LoadPixelScene`.
    *   It also loads additional structural elements from `hall_bottom.png` and `inside_bottom_right.png` to construct the biome's layout.

### Loaded Scenes

*   `data/biome_impl/secret_entrance.png`
*   `data/biome_impl/secret_entrance_visual.png`
*   `data/biome_impl/mountain/hall_bottom.png`
*   `data/biome_impl/mountain/inside_bottom_right.png`

## Enemy Spawning Configuration

The biome defines specific tables for enemy and prop spawning, influencing the types and quantities of entities encountered.

### `g_small_enemies` Table

This table defines the probability and count for various "small" enemy types that can spawn within the biome.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group of enemies (used internally).           |
| `prob`      | Individual probability of this specific entity spawning.                 |
| `min_count` | Minimum number of this entity to spawn.                                  |
| `max_count` | Maximum number of this entity to spawn.                                  |
| `entity`    | Path to the entity's XML definition.                                     |
| `entities`  | A list of entity paths for weighted random selection within a group.     |

**Key Entities and Probabilities:**

*   **`data/entities/animals/drone_physics.xml`**: `prob = 0.4`, `min_count = 1`, `max_count = 2`
*   **`data/entities/animals/lasershooter.xml`**: `prob = 0.1`, `min_count = 1`, `max_count = 1`
*   **`data/entities/animals/roboguard.xml`**: `prob = 0.1`, `min_count = 1`, `max_count = 1`
*   **`data/entities/animals/assassin.xml`**: `prob = 0.1`, `min_count = 1`, `max_count = 1`
*   **`data/entities/animals/acidshooter.xml`**: `prob = 0.1`, `min_count = 1`, `max_count = 1`
*   **`data/entities/animals/blob.xml`**: `prob = 0.3`, `min_count = 3`, `max_count = 5`
*   **`data/entities/animals/bigzombie.xml`**: `prob = 0.3`, `min_count = 1`, `max_count = 2`
*   **Weighted Group (Sniper/Flamer)**: `prob = 0.08`, `min_count = 1`, `max_count = 2` (randomly selects between `sniper.xml` and `flamer.xml`)

### `g_candles` Table

This table defines the probability and count for different types of physics candles that can spawn.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for this group of props.                               |
| `prob`      | Individual probability of this specific prop spawning.                   |
| `min_count` | Minimum number of this prop to spawn.                                    |
| `max_count` | Maximum number of this prop to spawn.                                    |
| `entity`    | Path to the prop's XML definition.                                       |

**Key Entities and Probabilities:**

*   **`data/entities/props/physics_candle_1.xml`**: `prob = 0.33`, `min_count = 1`, `max_count = 1`
*   **`data/entities/props/physics_candle_2.xml`**: `prob = 0.33`, `min_count = 1`, `max_count = 1`
*   **`data/entities/props/physics_candle_3.xml`**: `prob = 0.33`, `min_count = 1`, `max_count = 1`

## Spawn Function Registrations

The `RegisterSpawnFunction` calls link specific color values in the biome's pixel data to corresponding Lua functions.

### Key Registrations

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Associates the color `0xffffeedd` with the `init` function, triggering biome setup.
*   **`RegisterSpawnFunction( 0xffC8C800, "spawn_lamp2" )`**: Associates the color `0xffC8C800` with the `spawn_lamp2` function, likely for placing specific lamps.

## Helper Spawn Functions

These functions are called by the game engine based on the `RegisterSpawnFunction` calls and biome data.

### `spawn_lamp2(x, y)`

*   Spawns a lamp entity at a specific offset relative to the given coordinates.
*   Uses the `g_lamp2` global table (not fully defined in this snippet, but implied).

### `spawn_small_enemies(x, y)`

*   Spawns enemies defined in the `g_small_enemies` table at the given coordinates.

### `spawn_lamp(x, y)`

*   This function is defined but currently returns immediately, meaning it does not spawn any lamps.

### `spawn_potions(x, y)`

*   This function is defined but has no implementation, meaning it does not spawn any potions.