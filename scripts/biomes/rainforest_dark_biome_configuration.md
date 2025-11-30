---
title: Rainforest Dark Biome Configuration
category: scripts/biomes
---

```

# Rainforest Dark Biome Configuration

This document details the configuration for the "Rainforest Dark" biome in Noita, focusing on the entities and elements that can spawn within it. This script defines various spawn tables and functions that the game uses to populate the environment.

## Core Biome Initialization

The `init` function is called when the biome is first loaded. It applies a global modifier to the biome.

### Key Modifiers:

*   `FOG_OF_WAR_REAPPEARS`: This modifier ensures that the fog of war mechanics are active and reappear within this biome.

## Spawn Functions

The script registers several functions to be called at specific points or based on certain conditions during level generation.

### Registered Spawn Functions:

*   `init`: Called during biome initialization.
*   `spawn_scavengers`: Handles the spawning of scavenger-type enemies.
*   `spawn_large_enemies`: Manages the spawning of larger, more formidable enemies.
*   `spawn_lamp2`: Responsible for spawning specific types of lamps.
*   `load_pixel_scene4`: Loads a specific pixel scene, though its implementation is commented out.
*   `spawn_vines`: Handles the spawning of vine entities.
*   `spawn_dragonspot`: Intended for spawning dragon-related entities, but currently has no implementation.
*   `spawn_root_grower`: Manages the spawning of root grower entities.
*   `spawn_tree`: Intended for spawning tree entities, but currently has no implementation.

## Enemy Spawn Tables

These tables define the probability and count of various enemies that can spawn in the Rainforest Dark biome. The `total_prob` is calculated by summing the `prob` values of all entries.

### `g_small_enemies`

This table defines the probability distribution for smaller enemies.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                                          |
| :------------------- | :---------------------- | :---------------------- | :---------------------------------------------- |
| 0.5                  | 0                       | 0                       | "" (No spawn)                                   |
| 0.09                 | 1                       | 1                       | `data/entities/animals/lukki/lukki_creepy_long.xml` |
| 0.09                 | 1                       | 1                       | `data/entities/animals/lukki/lukki.xml`         |
| 0.1                  | 1                       | 2                       | `data/entities/animals/lurker.xml`              |
| 0.2                  | 1                       | 1                       | `data/entities/animals/lukki/lukki_dark.xml`    |
| 0.01                 | 1                       | 3                       | `data/entities/animals/wizard_weaken.xml`       |
| 0.06                 | 1                       | 3                       | `data/entities/animals/wizard_twitchy.xml`      |
| 0.06                 | 1                       | 3                       | `data/entities/animals/wizard_homing.xml`       |

### `g_big_enemies`

This table defines the probability distribution for larger enemies.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                                    | `ngpluslevel` |
| :------------------- | :---------------------- | :---------------------- | :---------------------------------------- | :------------ |
| 0.6                  | 0                       | 0                       | "" (No spawn)                             |               |
| 0.1                  | 2                       | 3                       | `data/entities/animals/rainforest/fungus.xml` |               |
| 0.1                  | 2                       | 3                       | `data/entities/animals/fungus_big.xml`    |               |
| 0.09                 | 1                       | 1                       | `data/entities/animals/lukki/lukki_dark.xml` |               |
| 0.1                  | 1                       | 1                       | `data/entities/animals/lurker.xml`        |               |
| 0.09                 | 1                       | 1                       | `data/entities/animals/lukki/lukki.xml`   |               |
| 0.03                 | 1                       | 1                       | `data/entities/animals/wizard_dark.xml`   |               |
| 0.03                 | 1                       | 1                       | `data/entities/animals/wizard_hearty.xml` |               |
| 0.01                 | 1                       | 1                       | `data/entities/animals/necrobot.xml`      | 1             |
| 0.01                 | 1                       | 1                       | `data/entities/animals/necrobot_super.xml`| 2             |

### `g_unique_enemy`

This table defines the probability distribution for unique enemies.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                          |
| :------------------- | :---------------------- | :---------------------- | :------------------------------ |
| 1.0                  | 0                       | 0                       | "" (No spawn)                   |
| 0.1                  | 1                       | 1                       | `data/entities/animals/drone_shield.xml` |
| 0.1                  | 1                       | 1                       | `data/entities/animals/lurker.xml` |
| 0.09                 | 1                       | 1                       | `data/entities/animals/lukki/lukki_dark.xml` |

### `g_unique_enemy2`

This table defines the probability distribution for a second type of unique enemy.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                               |
| :------------------- | :---------------------- | :---------------------- | :----------------------------------- |
| 1.0                  | 0                       | 0                       | "" (No spawn)                        |
| 1.0                  | 1                       | 1                       | `data/entities/buildings/lukki_eggs.xml` |
| 0.09                 | 1                       | 1                       | `data/entities/animals/lukki/lukki_dark.xml` |

### `g_large_enemies`

This table defines the probability distribution for large enemies, separate from `g_big_enemies`.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                                |
| :------------------- | :---------------------- | :---------------------- | :------------------------------------ |
| 0.4                  | 0                       | 0                       | "" (No spawn)                         |
| 0.1                  | 1                       | 1                       | `data/entities/animals/lurker.xml`    |
| 0.1                  | 1                       | 2                       | `data/entities/animals/rainforest/fungus.xml` |
| 0.5                  | 1                       | 2                       | `data/entities/animals/fungus_big.xml` |
| 0.09                 | 1                       | 1                       | `data/entities/animals/lukki/lukki_dark.xml` |
| 0.2                  | 1                       | 1                       | `data/entities/animals/crypt/skullfly.xml` |

## Item Spawn Tables

These tables define the probability and count of items that can spawn.

### `g_items`

This table defines the probability distribution for items, primarily wands.

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                               |
| :------------------- | :---------------------- | :---------------------- | :----------------------------------- |
| 0                    | 0                       | 0                       | "" (No spawn)                        |
| 5                    | 1                       | 1                       | `data/entities/items/wand_level_04.xml` |
| 3                    | 1                       | 1                       | `data/entities/items/wand_level_05.xml` |
| 3                    | 1                       | 1                       | `data/entities/items/wand_unshuffle_03.xml` |
| 3                    | 1                       | 1                       | `data/entities/items/wand_unshuffle_04.xml` |
| 5                    | 1                       | 1                       | `data/entities/items/wand_level_05_better.xml` |

## Prop and Environmental Element Spawn Tables

These tables define the probability and count of various props and environmental elements.

### `g_props`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                                       |
| :------------------- | :---------------------- | :---------------------- | :------------------------------------------- |
| 2.5                  | 0                       | 0                       | "" (No spawn)                                |
| 0.5                  | 1                       | 1                       | `data/entities/props/physics_barrel_radioactive.xml` |
| 0.1                  | 1                       | 1                       | `data/entities/props/physics_fungus_small.xml` |
| 0.1                  | 1                       | 1                       | `data/entities/props/physics_fungus.xml`     |
| 0.08                 | 1                       | 1                       | `data/entities/props/physics_fungus_big.xml` |

### `g_lamp`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                                   |
| :------------------- | :---------------------- | :---------------------- | :--------------------------------------- |
| 0.3                  | 1                       | 1                       | "" (No spawn)                            |
| 0.6                  | 1                       | 1                       | `data/entities/props/physics_torch_stand_blue.xml` |
| 1.0                  | 1                       | 1                       | `data/entities/props/physics_fungus_small.xml` |
| 1.0                  | 1                       | 1                       | `data/entities/props/physics_fungus.xml`     |
| 0.5                  | 1                       | 1                       | `data/entities/props/physics_fungus_big.xml` |

### `g_lamp2`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity |
| :------------------- | :---------------------- | :---------------------- | :----- |
| 0.0                  | 1                       | 1                       | ""     |

### `g_ghostlamp`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Offset Y (`offset_y`) | Entity                                       |
| :------------------- | :---------------------- | :---------------------- | :-------------------- | :------------------------------------------- |
| 1.0                  | 1                       | 1                       | 10                    | `data/entities/props/physics_chain_torch_ghostly.xml` |

### `g_candles`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                         |
| :------------------- | :---------------------- | :---------------------- | :----------------------------- |
| 0.33                 | 1                       | 1                       | `data/entities/props/physics_candle_1.xml` |
| 0.33                 | 1                       | 1                       | `data/entities/props/physics_candle_2.xml` |
| 0.33                 | 1                       | 1                       | `data/entities/props/physics_candle_3.xml` |

### `g_vines`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity                                           |
| :------------------- | :---------------------- | :---------------------- | :----------------------------------------------- |
| 0.5                  | 1                       | 1                       | "" (No spawn)                                    |
| 0.4                  | 1                       | 1                       | `data/entities/verlet_chains/vines/verlet_vine_dark.xml` |
| 0.3                  | 1                       | 1                       | `data/entities/verlet_chains/vines/verlet_vine_dark_long.xml` |
| 0.5                  | 1                       | 1                       | `data/entities/verlet_chains/vines/verlet_vine_dark_short.xml` |
| 0.5                  | 1                       | 1                       | `data/entities/verlet_chains/vines/verlet_vine_dark_shorter.xml` |

## Pixel Scene Definitions

These tables define the pixel scenes that can be loaded into the biome.

### `g_pixel_scene_01`

| Probability (`prob`) | Material File (`material_file`)                 | Visual File (`visual_file`) | Background File (`background_file`) | Is Unique (`is_unique`) |
| :------------------- | :---------------------------------------------- | :-------------------------- | :---------------------------------- | :---------------------- |
| 0.5                  | `data/biome_impl/rainforest/pit01.png`          | ""                          | ""                                  | 0                       |
| 0.5                  | `data/biome_impl/rainforest/pit02.png`          | ""                          | ""                                  | 0                       |
| 0.5                  | `data/biome_impl/rainforest/pit03.png`          | ""                          | ""                                  | 0                       |

### `g_pixel_scene_02`

| Probability (`prob`) | Material File (`material_file`)                   | Visual File (`visual_file`) | Background File (`background_file`) | Is Unique (`is_unique`) |
| :------------------- | :------------------------------------------------ | :-------------------------- | :---------------------------------- | :---------------------- |
| 0.5                  | `data/biome_impl/rainforest/hut03.png`            | ""                          | ""                                  | 0                       |
| 1.2                  | `data/biome_impl/rainforest/symbolroom.png`       | ""                          | ""                                  | 0                       |

## Other Spawn Tables

### `g_nest`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity |
| :------------------- | :---------------------- | :---------------------- | :----- |
| 0.5                  | 1                       | 1                       | ""     |

### `g_scavengers`

| Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Entity |
| :------------------- | :---------------------- | :---------------------- | :----- |
| 0.5                  | 0                       | 0                       | ""     |

## Specific Spawn Functions

These functions are called by the game to spawn specific elements within the biome.

### `spawn_small_enemies(x, y)`

Spawns small enemies based on the `g_small_enemies` table.

### `spawn_big_enemies(x, y)`

Spawns big enemies based on the `g_big_enemies` table.

### `spawn_unique_enemy(x, y)`

Spawns unique enemies based on the `g_unique_enemy` table, with a slight vertical offset.

### `spawn_unique_enemy2(x, y)`

Spawns a second type of unique enemy based on the `g_unique_enemy2` table.

### `spawn_items(x, y)`

Spawns items, specifically a wand altar if a random condition is met.

### `spawn_nest(x, y)`

This function is defined but commented out, meaning nests do not spawn by default.

### `spawn_props(x, y)`

Spawns props based on the `g_props` table.

### `spawn_scavengers(x, y)`

This function is defined but commented out, meaning scavengers do not spawn by default.

### `spawn_large_enemies(x, y)`

Spawns large enemies based on the `g_large_enemies` table.

### `spawn_lamp(x, y)`

Spawns lamps based on the `g_lamp` table, with a vertical offset.

### `spawn_lamp2(x, y)`

Spawns elements defined in `g_lamp2`, with positional offsets.

### `load_pixel_scene(x, y)`

Loads a random pixel scene from `g_pixel_scene_01`.

### `load_pixel_scene2(x, y)`

Loads a random pixel scene from `g_pixel_scene_02`.

### `load_pixel_scene4(x, y)`

This function is defined but commented out, meaning no pixel scene is loaded by default.

### `spawn_vines(x, y)`

Spawns vines based on the `g_vines` table, with a chance for an additional spawn.

### `spawn_dragonspot(x, y)`

This function is defined but has no implementation, so no dragon spots will spawn.

### `spawn_tree(x, y)`

This function is defined but has no implementation, so no trees will spawn.

### `spawn_root_grower(x, y)`

Spawns a root grower entity with a 50% probability based on coordinates.