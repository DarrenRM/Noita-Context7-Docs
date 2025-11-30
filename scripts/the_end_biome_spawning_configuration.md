---
title: The End Biome Spawning Configuration
category: scripts
---

# The End Biome Spawning Configuration

This document details the spawning configurations for entities within "The End" biome in Noita, as defined by the `the_end.lua` script. It outlines the probabilities and types of enemies, items, and props that can appear in this biome.

## Core Functionality

The script primarily defines tables that hold spawn data for various entity types. These tables are then used by `spawn` and `load_pixel_scene` functions to populate the game world.

### Key Spawn Functions

*   `spawn_small_enemies(x, y)`: Spawns smaller enemies. If the `y` coordinate is below -7000, it uses `g_small_enemies_sky`; otherwise, it uses `g_small_enemies`.
*   `spawn_big_enemies(x, y)`: Spawns larger enemies. Similar to `spawn_small_enemies`, it differentiates between sky and ground spawns based on the `y` coordinate.
*   `spawn_items(x, y)`: Handles the spawning of items, with a specific chance to load a wand altar pixel scene.
*   `spawn_lamp(x, y)`: Spawns a physics torch stand.
*   `spawn_props(x, y)`: Spawns general props.
*   `spawn_unique_enemy(x, y)`: Spawns a unique enemy, currently configured to spawn an `arrowtrap_right`.
*   `spawn_large_enemies(x, y)`: Spawns large enemies, currently configured to spawn an `arrowtrap_left`.
*   `spawn_moon(x, y)`: Spawns either a `moon_altar` or `dark_moon_altar` based on the `y` coordinate.
*   `spawn_chest(x, y)`: Spawns either a `chest_random_super` or `chest_random` with a low probability for the super variant.
*   `spawn_shopitem(x, y)`: Generates shop items, with a special condition for higher-level items outside a specific vertical range.
*   `spawn_specialshop(x, y)`: Similar to `spawn_shopitem`, it generates shop items with a focus on higher-level items outside a specific vertical range.

## Entity Spawn Tables

These tables define the entities that can spawn and their associated probabilities.

### `g_small_enemies`

This table defines the probability distribution for smaller enemies that can spawn on the ground.

| Probability | Min Count | Max Count | Entity                                         | Notes                                    |
| :---------- | :-------- | :-------- | :--------------------------------------------- | :--------------------------------------- |
| 0.4         | 0         | 0         | ""                                             | Represents air, no spawns.               |
| 0.2         | 1         | 1         | `data/entities/animals/the_end/gazer.xml`      |                                          |
| 0.2         | 1         | 1         | `data/entities/animals/the_end/spitmonster.xml`|                                          |
| 0.2         | 1         | 1         | `data/entities/animals/the_end/bloodcrystal_physics.xml` |                                          |
| 0.01        | 1         | 1         | `data/entities/animals/the_end/worm_end.xml`   | Low probability for a worm.              |
| 0.004       | 1         | 1         | `data/entities/animals/wraith.xml`             | Very low probability for a wraith.       |
| 0.001       | 1         | 1         | `data/entities/animals/wraith_glowing.xml`     | Extremely low probability for a glowing wraith. |
| 0.1         | 1         | 2         | `data/entities/animals/thunderskull.xml`       |                                          |

### `g_small_enemies_sky`

This table defines the probability distribution for smaller enemies that can spawn in the sky.

| Probability | Min Count | Max Count | Entity                                         | Notes                                    |
| :---------- | :-------- | :-------- | :--------------------------------------------- | :--------------------------------------- |
| 0.4         | 0         | 0         | ""                                             | Represents air, no spawns.               |
| 0.1         | 1         | 1         | `data/entities/animals/the_end/skygazer.xml`   |                                          |
| 0.2         | 1         | 1         | `data/entities/animals/the_end/spearbot.xml`   |                                          |
| 0.2         | 1         | 1         | `data/entities/animals/the_end/skycrystal_physics.xml` |                                          |
| 0.01        | 1         | 1         | `data/entities/animals/the_end/worm_skull.xml` | Low probability for a skull worm.        |
| 0.004       | 1         | 1         | `data/entities/animals/wraith_storm.xml`       | Very low probability for a storm wraith. |
| 0.001       | 1         | 1         | `data/entities/animals/wraith_glowing.xml`     | Extremely low probability for a glowing wraith. |
| 0.1         | 1         | 2         | `data/entities/animals/thunderskull.xml`       |                                          |
| 0.1         | 1         | 2         | `data/entities/animals/wizard_tele.xml`        |                                          |
| 0.04        | 1         | 1         | `data/entities/animals/thundermage_big.xml`    |                                          |

### `g_big_enemies_sky`

This table defines the probability distribution for larger enemies that can spawn in the sky.

| Probability | Min Count | Max Count | Entity                               | Notes                                    |
| :---------- | :-------- | :-------- | :----------------------------------- | :--------------------------------------- |
| 1.8         | 0         | 0         | ""                                   | Represents air, no spawns.               |
| 0.03        | 1         | 1         | `data/entities/animals/wraith.xml`   | Very low probability for a wraith.       |
| 0.03        | 1         | 1         | `data/entities/animals/wraith_glowing.xml` | Extremely low probability for a glowing wraith. |

### `g_items`

This table defines the probability distribution for items that can spawn.

| Probability | Min Count | Max Count | Entity                           | Notes                                    |
| :---------- | :-------- | :-------- | :------------------------------- | :--------------------------------------- |
| 0           | 0         | 0         | ""                               | No spawns at this probability.           |
| 5           | 1         | 1         | `data/entities/items/wand_level_04.xml` | Spawns a level 4 wand.                   |

### `g_lamp`

This table defines the probability distribution for lamp-related props.

| Probability | Min Count | Max Count | Entity                               | Notes                                    |
| :---------- | :-------- | :-------- | :----------------------------------- | :--------------------------------------- |
| 0.3         | 1         | 1         | ""                                   | No spawn.                                |
| 0.6         | 1         | 1         | `data/entities/props/physics_torch_stand.xml` | Spawns a physics torch stand.            |

### `g_props`

This table defines the probability distribution for general props.

| Probability | Min Count | Max Count | Offset Y | Entity | Notes                                    |
| :---------- | :-------- | :-------- | :------- | :----- | :--------------------------------------- |
| 1           | 1         | 1         | -4       | ""     | Default, no prop spawned.                |

*Note: The commented-out `spike.xml` entry suggests potential future or experimental prop additions.*

### `g_unique_enemy`

This table defines the probability distribution for unique enemies.

| Probability | Min Count | Max Count | Offset X | Entity                                 | Notes                                    |
| :---------- | :-------- | :-------- | :------- | :------------------------------------- | :--------------------------------------- |
| 0.1         | 0         | 0         | 0        | ""                                     | Represents air, no spawns.               |
| 1.0         | 1         | 1         | 2        | `data/entities/buildings/arrowtrap_right.xml` | Spawns an arrow trap to the right.       |

### `g_large_enemies`

This table defines the probability distribution for large enemies.

| Probability | Min Count | Max Count | Offset X | Entity                                | Notes                                    |
| :---------- | :-------- | :-------- | :------- | :------------------------------------ | :--------------------------------------- |
| 0.1         | 0         | 0         | 0        | ""                                    | Represents air, no spawns.               |
| 1.0         | 1         | 1         | 1        | `data/entities/buildings/arrowtrap_left.xml` | Spawns an arrow trap to the left.        |

### `g_pixel_scene_01`

This table defines pixel scenes that can be loaded.

| Probability | Material File                               | Visual File | Background File | Is Unique |
| :---------- | :------------------------------------------ | :---------- | :-------------- | :-------- |
| 1.0         | `data/biome_impl/crypt/cathedral.png`       | ""          | ""              | 0         |
| 1.0         | `data/biome_impl/crypt/mining.png`          | ""          | ""              | 0         |

### `g_ghostlamp`

This table defines the probability distribution for ghost lamps.

| Probability | Min Count | Max Count | Entity                                       | Notes                                    |
| :---------- | :-------- | :-------- | :------------------------------------------- | :--------------------------------------- |
| 1.0         | 1         | 1         | `data/entities/props/physics_chain_torch_ghostly.xml` | Spawns a ghostly chain torch.            |

## Unused or Placeholder Functions

Several functions are defined but currently have no implementation or are placeholders.

*   `spawn_apparition()`
*   `spawn_potions(x, y)`
*   `spawn_heart(x, y)`
*   `load_pixel_scene3(x, y)`
*   `load_pixel_scene4(x, y)`
*   `spawn_wands()`
*   `spawn_potion_altar()`
*   `load_pixel_scene2(x, y)` (Redefined, first instance is used)
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_stash(x, y)`
*   `spawn_nest(x, y)`
*   `spawn_altar_torch(x, y)`
*   `spawn_skulls(x, y)`
*   `spawn_trapwand(x, y)`
*   `spawn_bbqbox(x, y)`
*   `load_structures(x, y)`
*   `load_large_structures(x, y)`
*   `load_i_structures(x, y)`
*   `load_oiltank(x, y)`
*   `load_oiltank_alt(x, y)`
*   `load_altar(x, y)`