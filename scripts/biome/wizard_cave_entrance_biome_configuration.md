---
title: Wizard Cave Entrance Biome Configuration
category: scripts/biome
---

# Wizard Cave Entrance Biome Configuration

This document details the configuration for the Wizard Cave Entrance biome in Noita, focusing on entity spawning and visual setup.

## Core Biome Setup

The biome is initialized by loading specific pixel scenes for its geometry, visual appearance, and background.

*   **`init(x, y, w, h)`**: This function is called during biome initialization.
    *   Loads the primary biome geometry: `data/biome_impl/wizardcave_entrance.png`
    *   Loads the visual layer: `data/biome_impl/wizardcave_entrance_visual.png`
    *   Loads the background layer: `data/biome_impl/wizardcave_entrance_background.png`
    *   `x`, `y`, `w`, `h` define the biome's position and dimensions.

*   **`spawn_gate(x, y)`**: Spawns the entrance gate entity.
    *   Entity: `data/entities/buildings/wizardcave_gate.xml`
    *   Position: `x`, `y+55` (slightly offset vertically).

## Entity Spawning Configurations

The following tables define the probabilities and types of entities that can spawn within this biome. The `total_prob` is calculated by summing individual `prob` values.

### Small Enemies

This table defines the potential small enemies that can spawn.

| Probability | Min Count | Max Count | Entity                               | Notes                               |
| :---------- | :-------- | :-------- | :----------------------------------- | :---------------------------------- |
| 0.3         | 0         | 0         | ""                                   | No spawns at this probability level |
| 0.1         | 1         | 2         | `data/entities/animals/wand_ghost.xml` | Wand Ghosts                         |

### Big Enemies

This table defines the potential larger enemies that can spawn.

| Probability | Min Count | Max Count | Entity                                       | Notes                               |
| :---------- | :-------- | :-------- | :------------------------------------------- | :---------------------------------- |
| 0.3         | 0         | 0         | ""                                           | No spawns at this probability level |
| 0.1         | 1         | 1         | `data/entities/animals/statue_physics.xml`   | Physics Statue                      |
| 0.2         | 1         | 1         | `data/entities/animals/phantom_a.xml`        | Phantom A                           |
| 0.2         | 1         | 1         | `data/entities/animals/phantom_b.xml`        | Phantom B                           |
| 0.09        | 1         | 1         | `data/entities/animals/necromancer.xml`      | Necromancer                         |
| 0.09        | 1         | 1         | `data/entities/animals/wizard_returner.xml`  | Wizard Returner                     |
| 0.08        | 1         | 1         | `data/entities/animals/wizard_neutral.xml`   | Neutral Wizard                      |
| 0.04        | 1         | 1         | `data/entities/animals/wizard_hearty.xml`    | Hearty Wizard                       |
| 0.01        | 1         | 1         | `data/entities/animals/wraith_glowing.xml`   | Glowing Wraith                      |
| 0.02        | 1         | 1         | `data/entities/animals/enlightened_alchemist.xml` | Enlightened Alchemist               |
| 0.02        | 1         | 1         | `data/entities/animals/failed_alchemist.xml` | Failed Alchemist                    |

### Lamps

Defines the types of lamps that can spawn.

*   **`g_lamp`**:
    | Probability | Min Count | Max Count | Entity                                     |
    | :---------- | :-------- | :-------- | :----------------------------------------- |
    | 1.0         | 1         | 1         | `data/entities/props/physics/chain_torch_ghostly.xml` |

*   **`g_ghostlamp`**:
    | Probability | Min Count | Max Count | Entity                                     |
    | :---------- | :-------- | :-------- | :----------------------------------------- |
    | 1.0         | 1         | 1         | `data/entities/props/physics/chain_torch_ghostly.xml` |

### Candles

Defines the types of candles that can spawn.

*   **`g_candles`**:
    | Probability | Min Count | Max Count | Entity                         |
    | :---------- | :-------- | :-------- | :----------------------------- |
    | 0.33        | 1         | 1         | `data/entities/props/physics_candle_1.xml` |
    | 0.33        | 1         | 1         | `data/entities/props/physics_candle_2.xml` |
    | 0.33        | 1         | 1         | `data/entities/props/physics_candle_3.xml` |

### Props

A general category for various props that can spawn in the biome.

| Probability | Min Count | Max Count | Offset Y | Entity                               | Notes                               |
| :---------- | :-------- | :-------- | :------- | :----------------------------------- | :---------------------------------- |
| 0.33        | 1         | 1         | -        | `data/entities/props/physics_candle_1.xml` | Candle 1                            |
| 0.33        | 1         | 1         | -        | `data/entities/props/physics_candle_2.xml` | Candle 2                            |
| 0.33        | 1         | 1         | -        | `data/entities/props/physics_candle_3.xml` | Candle 3                            |
| 5.4         | 1         | 1         | -        | ""                                   | No entity (empty slot)              |
| 0.6         | 1         | 1         | -        | `data/entities/props/physics_bone_01.xml`  | Bone 01                             |
| 0.6         | 1         | 1         | -        | `data/entities/props/physics_bone_02.xml`  | Bone 02                             |
| 0.6         | 1         | 1         | -        | `data/entities/props/physics_bone_03.xml`  | Bone 03                             |
| 0.6         | 1         | 1         | -        | `data/entities/props/physics_bone_04.xml`  | Bone 04                             |
| 0.6         | 1         | 1         | -        | `data/entities/props/physics_bone_05.xml`  | Bone 05                             |
| 0.6         | 1         | 1         | -        | `data/entities/props/physics_bone_06.xml`  | Bone 06                             |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_skull_01.xml` | Skull 01                            |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_skull_02.xml` | Skull 02                            |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_skull_03.xml` | Skull 03                            |

### Cloud Trap

Defines the spawning of cloud traps.

| Probability | Min Count | Max Count | Entity                           | Notes                               |
| :---------- | :-------- | :-------- | :------------------------------- | :---------------------------------- |
| 0.2         | 0         | 0         | ""                               | No spawns at this probability level |
| 0.3         | 1         | 1         | `data/entities/buildings/cloud_trap.xml` | Cloud Trap                          |

## Helper Functions

These functions are used internally for spawning specific entity types.

*   **`spawn_small_enemies(x, y)`**: Spawns entities defined in `g_small_enemies`.
*   **`spawn_big_enemies(x, y)`**: Spawns entities defined in `g_big_enemies`.
*   **`spawn_lamp(x, y)`**: Spawns entities defined in `g_lamp`.
*   **`spawn_props(x, y)`**: Spawns entities defined in `g_props` with a vertical offset of -3.

The following functions are defined but do not contain any implementation in this script:
*   `spawn_items(pos_x, pos_y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`
*   `spawn_potions(x, y)`
*   `spawn_wands(x, y)`