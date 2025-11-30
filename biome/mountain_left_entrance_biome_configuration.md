---
title: Mountain Left Entrance Biome Configuration
category: biome
---

---

# Mountain Left Entrance Biome Configuration

This document details the configuration for the "Mountain Left Entrance" biome in Noita, focusing on its entity spawning and visual setup.

## Biome Initialization and Spawning

The biome is initialized using a series of `RegisterSpawnFunction` calls, mapping specific color IDs within the biome's pixel data to corresponding Lua functions. These functions are responsible for loading entities and setting up the environment.

### Core Initialization Functions

*   **`init(x, y, w, h)`**: This is the primary initialization function. It loads several pixel scene files that define the biome's layout, visuals, and background elements. It dynamically chooses a background based on whether a gamepad is connected.
    *   `data/biome_impl/mountain/left_entrance_bottom.png`
    *   `data/biome_impl/mountain/left_stub_edge.png`
    *   `data/biome_impl/mountain/left_entrance.png` (main layout)
    *   `data/biome_impl/mountain/left_entrance_visual.png` (visual layer)
    *   `data/biome_impl/mountain/left_entrance_background_gamepad.png` (gamepad background)
    *   `data/biome_impl/mountain/left_entrance_background.png` (standard background)

### Registered Spawn Functions

These functions are triggered by specific color IDs in the biome's pixel data.

| Color ID | Function Name           | Description                                                              |
| :------- | :---------------------- | :----------------------------------------------------------------------- |
| `0xffffeedd` | `init`                  | Primary biome initialization.                                            |
| `0xffC4189B` | `spawn_trees`           | Spawns various spruce trees.                                             |
| `0xffC41820` | `spawn_big_bushes`      | Spawns large bushes and smaller plants.                                  |
| `0xffC41860` | `spawn_vines`           | Spawns different types of breakable vines.                               |
| `0xffc4186a` | `spawn_wasd`            | Spawns control prompts (WASD or analog stick) and a special prop.        |
| `0xffc45f7b` | `spawn_wasd_trigger`    | Spawns a trigger for WASD controls, only if the intro is not playing.    |
| `0xffc4186b` | `spawn_mouse`           | Spawns control prompts (mouse or LT button).                             |
| `0xffc4187b` | `spawn_mouse_trigger`   | Spawns a trigger for mouse controls.                                     |
| `0xffc4187c` | `spawn_grass`           | Spawns specific grass entities for the left entrance.                    |
| `0xffff5a0f` | `spawn_music_trigger`   | Spawns a music trigger entity.                                           |
| `0xff80FF5A` | `spawn_vines_b`         | Spawns vines (alias for `spawn_vines`).                                  |

## Entity Spawning Definitions

The following tables define the entities that can be spawned within this biome, along with their probabilities and spawn parameters.

### `g_trees`

Spawns various spruce tree entities.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `prob`      | `1.0`                               | Probability of spawning this entity.      |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/vegetation/tree_*.xml` | Path to the tree entity XML file.         |

### `g_big_bushes`

Spawns large bushes and smaller plant entities.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `prob`      | `1.0`                                     | Probability of spawning this entity.      |
| `min_count` | `1`                                       | Minimum number of entities to spawn.      |
| `max_count` | `1`                                       | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/vegetation/plant_bush_*.xml` | Path to the bush/plant entity XML file. |

### `g_vines`

Spawns different lengths and types of breakable vines.

| Attribute   | Value                                           | Description                               |
| :---------- | :---------------------------------------------- | :---------------------------------------- |
| `prob`      | `0.4` to `1.5`                                  | Probability of spawning this entity.      |
| `min_count` | `1`                                             | Minimum number of entities to spawn.      |
| `max_count` | `1`                                             | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/verlet_chains/vines/verlet_vine*.xml` | Path to the vine entity XML file.       |
| `entity`    | `""`                                            | Represents no vine spawn (with `prob=1.5`). |

### `g_props`

Spawns various physics-based stone props.

| Attribute   | Value                                 | Description                               |
| :---------- | :------------------------------------ | :---------------------------------------- |
| `prob`      | `0.2` to `0.5`                        | Probability of spawning this entity.      |
| `min_count` | `0` to `1`                            | Minimum number of entities to spawn.      |
| `max_count` | `0` to `1`                            | Maximum number of entities to spawn.      |
| `offset_y`  | `0`                                   | Vertical offset for spawning.             |
| `entity`    | `data/entities/props/physics_stone_*.xml` | Path to the stone prop entity XML file. |
| `entity`    | `""`                                  | Represents no prop spawn (with `prob=0.2`). |

### `g_surprise`

Spawns a special prop with a conditional spawn.

| Attribute   | Value                               | Description