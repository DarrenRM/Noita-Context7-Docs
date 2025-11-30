---
title: Endgame Biome Configuration
category: scripts
---

---

# Endgame Biome Configuration

This document details the configuration for the endgame biome in Noita, focusing on its script-based elements for AI-assisted modding.

## Biome Initialization

The `init` function is the primary entry point for setting up the biome. It's responsible for loading the visual assets and defining the initial state of the biome.

### `init(x, y, w, h)`

*   **Purpose**: Initializes the endgame biome at the specified coordinates.
*   **Parameters**:
    *   `x`, `y`: The starting coordinates for the biome.
    *   `w`, `h`: The width and height of the biome area (often not directly used in this function but part of the standard biome initialization signature).
*   **Core Action**: Calls `LoadPixelScene` to load the biome's visual representation and background.
    *   `data/biome_impl/endgame2.png`: The main pixel data for the biome.
    *   `""`: An empty string, indicating no specific material mapping is applied here.
    *   `x`, `y`: The position where the scene is loaded.
    *   `data/biome_impl/endgame2_background.png`: The background image for the biome.
    *   `true`: Indicates that the background should be loaded.

## Entity Spawning Configurations

The following tables define the probability and types of entities that can spawn within this biome. These are crucial for controlling enemy encounters and environmental props.

### `g_small_enemies`

This table defines the distribution of smaller enemy types that can spawn in the biome.

| Attribute   | Value                                      | Description                                                                 |
| :---------- | :----------------------------------------- | :-------------------------------------------------------------------------- |
| `total_prob`| `0`                                        | Placeholder, actual probabilities are defined within the nested tables.     |
| `prob`      | `0.65`                                     | Probability of spawning nothing (air).                                      |
| `min_count` | `0`                                        | Minimum count for this spawn entry.                                         |
| `max_count` | `0`                                        | Maximum count for this spawn entry.                                         |
| `entity`    | `""`                                       | No entity spawned for this probability.                                     |
| `prob`      | `0.05`                                     | Probability of spawning `phantom_a`.                                        |
| `min_count` | `1`                                        | Minimum count for `phantom_a`.                                              |
| `max_count` | `1`                                        | Maximum count for `phantom_a`.                                              |
| `entity`    | `"data/entities/animals/phantom_a.xml"`    | Entity to spawn (Phantom A).                                                |
| `prob`      | `0.3`                                      | Probability of spawning `skullrat`.                                         |
| `min_count` | `3`                                        | Minimum count for `skullrat`.                                               |
| `max_count` | `4`                                        | Maximum count for `skullrat`.                                               |
| `entity`    | `"data/entities/animals/skullrat.xml"`     | Entity to spawn (Skullrat).                                                 |
| `prob`      | `0.05`                                     | Probability of spawning `phantom_b`.                                        |
| `min_count` | `1`                                        | Minimum count for `phantom_b`.                                              |
| `max_count` | `1`                                        | Maximum count for `phantom_b`.                                              |
| `entity`    | `"data/entities/animals/phantom_b.xml"`    | Entity to spawn (Phantom B).                                                |
| `prob`      | `0.2`                                      | Probability of spawning `skullfly`.                                         |
| `min_count` | `1`                                        | Minimum count for `skullfly`.                                               |
| `max_count` | `1`                                        | Maximum count for `skullfly`.                                               |
| `entity`    | `"data/entities/animals/skullfly.xml"`     | Entity to spawn (Skullfly).                                                 |
| `prob`      | `0.1`                                      | Probability of spawning `acidshooter`.                                      |
| `min_count` | `1`                                        | Minimum count for `acidshooter`.                                            |
| `max_count` | `1`                                        | Maximum count for `acidshooter`.                                            |
| `entity`    | `"data/entities/animals/acidshooter.xml"` | Entity to spawn (Acid Shooter).                                             |
| `prob`      | `0.1`                                      | Probability of spawning `crystal_physics`.                                  |
| `min_count` | `1`                                        | Minimum count for `crystal_physics`.                                        |
| `max_count` | `1`                                        | Maximum count for `crystal_physics`.                                        |
| `entity`    | `"data/entities/animals/crystal_physics.xml"`| Entity to spawn (Crystal Physics).                                          |

### `g_lamp2`

This table defines the props related to lamps and chandeliers that can spawn.

| Attribute   | Value                                          | Description                                                                 |
| :---------- | :--------------------------------------------- | :-------------------------------------------------------------------------- |
| `total_prob`| `0`                                            | Placeholder.                                                                |
| `prob`      | `0.0`                                          | Probability of spawning nothing.                                            |
| `min_count` | `1`                                            | Minimum count.                                                              |
| `max_count` | `1`                                            | Maximum count.                                                              |
| `entity`    | `""`                                           | No entity.                                                                  |
| `prob`      | `1.0`                                          | Probability of spawning `physics_chain_torch`.                              |
| `min_count` | `1`                                            | Minimum count.                                                              |
| `max_count` | `1`                                            | Maximum count.                                                              |
| `entity`    | `"data/entities/props/physics_chain_torch.xml"`| Entity to spawn (Physics Chain Torch).                                      |
| `prob`      | `1.0`                                          | Probability of spawning `physics_chandelier`.                               |
| `min_count` | `1`                                            | Minimum count.                                                              |
| `max_count` | `1`                                            | Maximum count.                                                              |
| `offset_x`  | `5`                                            | X-axis offset for the chandelier.                                           |
| `offset_y`  | `6`                                            | Y-axis offset for the chandelier.                                           |
| `entity`    | `"data/entities/props/physics_chandelier.xml"` | Entity to spawn (Physics Chandelier).                                       |

### `g_candles`

This table defines the distribution of different types of candles that can spawn.

| Attribute   | Value                                     | Description                                |
| :---------- | :---------------------------------------- | :----------------------------------------- |
| `total_prob`| `0`                                       | Placeholder.                               |
| `prob`      | `0.33`                                    | Probability of spawning `candle_1`.        |
| `min_count` | `1`                                       | Minimum count.                             |
| `max_count` | `1`                                       | Maximum count.                             |
| `entity`    | `"data/entities/props/physics_candle_1.xml"`| Entity to spawn (Physics Candle 1).        |
| `prob`      | `0.33`                                    | Probability of spawning `candle_2`.        |
| `min_count` | `1`                                       | Minimum count.                             |
| `max_count` | `1`                                       | Maximum count.                             |
| `entity`    | `"data/entities/props/physics_candle_2.xml"`| Entity to spawn (Physics Candle 2).        |
| `prob`      | `0.33`                                    | Probability of spawning `candle_3`.        |
| `min_count` | `1`                                       | Minimum count.                             |
| `max_count` | `1`                                       | Maximum count.                             |
| `entity`    | `"data/entities/props/physics_candle_3.xml"`| Entity to spawn (Physics Candle 3).        |

## Spawn Functions

These functions are registered to be called by the game's director system at specific times or under certain conditions.

### `RegisterSpawnFunction(id, function_name)`

*   **Purpose**: Registers a Lua function to be called by the game's director.
*   **Parameters**:
    *   `id`: A unique identifier (often a color code) associated with the spawn event.
        *   `0xffffeedd`: Associated with the `init` function.
        *   `0xffC8C800`: Associated with the `spawn_lamp2` function.
    *   `function_name`: The name of the Lua function to be called.

### `spawn_lamp2(x, y)`

*   **Purpose**: Spawns lamp-related entities at a specific location.
*   **Parameters**:
    *   `x`, `y`: The base coordinates for spawning.
*   **Core Action**: Calls the `spawn` utility function with the `g_lamp2` configuration, applying an offset to the provided `x` and `y` coordinates.

### `spawn_small_enemies(x, y)`

*   **Purpose**: Spawns small enemy entities at a specific location.
*   **Parameters**:
    *   `x`, `y`: The coordinates where enemies will spawn.
*   **Core Action**: Calls the `spawn` utility function with the `g_small_enemies` configuration.

## Dependencies

This script relies on external Lua files for core functionalities.

*   `dofile_once("data/scripts/director_helpers.lua")`: Provides utility functions for managing game directors and spawns.
*   `dofile_once("data/scripts/biome_scripts.lua")`: Contains general biome-related functions and definitions.