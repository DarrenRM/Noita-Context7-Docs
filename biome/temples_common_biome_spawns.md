---
title: Temples Common Biome Spawns
category: biome
---

# Temples Common Biome Spawns

This file defines common spawn functions and entity configurations used within the temples biomes in Noita. It acts as a central hub for registering various biome elements, from decorative props to specific enemy encounters and puzzle mechanics.

## Core Functionality

This script primarily registers functions that are called by the game's procedural generation system (the "wang generator") to populate biomes with specific content.

### Key Functions and Registrations

*   **`RegisterSpawnFunction( color_id, function_name )`**: This is the core mechanism for linking specific tile colors in the biome's pixel data to Lua functions that will spawn entities or effects at that location.
*   **`CHEST_LEVEL`**: A global variable indicating the level of items to be spawned from chests.
*   **`dofile_once(...)`**: Includes essential helper scripts for biome generation and director logic.

### Registered Spawn Functions

The following table lists some of the key spawn functions registered, along with their associated color IDs and a brief description of their purpose.

| Color ID   | Function Name                 | Description                                    |
| :--------- | :---------------------------- | :--------------------------------------------- |
| `0xff805000` | `spawn_cloud_trap`            | Spawns a cloud trap entity.                    |
| `0xff397780` | `load_floor_rubble`           | Loads dynamic floor rubble.                    |
| `0xff00ffa0` | `load_floor_rubble_l`         | Loads left-oriented floor rubble.              |
| `0xff1ca7ff` | `load_floor_rubble_r`         | Loads right-oriented floor rubble.             |
| `0xffffeed1` | `spawn_puzzle_watchtower`     | Spawns a watchtower puzzle element.            |
| `0xffffeedb` | `spawn_puzzle_potion_mimics`  | Spawns a potion mimic puzzle.                  |
| `0xffffeedc` | `spawn_puzzle_darkness`       | Spawns a darkness puzzle.                      |
| `0xffffeedd` | `spawn_boss`                  | Spawns a biome boss.                           |
| `0xffffeedf` | `spawn_potion_mimic`          | Spawns a potion mimic item.                    |
| `0xffffeed0` | `spawn_fish_many`             | Spawns multiple fish entities.                 |
| `0xffffeed3` | `spawn_book_barren`           | Spawns a barren book item.                     |
| `0xffffeed4` | `spawn_potion_beer`           | Spawns a beer potion item.                     |
| `0xffffeed5` | `spawn_potion_milk`           | Spawns a milk potion item.                     |
| `0xffffeed6` | `spawn_scorpion`              | Spawns a scorpion enemy.                       |
| `0xffaaaaaa` | `spawn_sign_left`             | Spawns a left-facing sign.                     |
| `0xffaadddd` | `spawn_sign_right`            | Spawns a right-facing sign.                    |

## Entity Group Definitions

These tables define collections of entities that can be spawned, often with associated probabilities and variations.

### `g_lamp`

Defines a single ghostly chain torch.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `prob`      | `1.0`                                     | Probability of spawning this item.        |
| `min_count` | `1`                                       | Minimum number of entities to spawn.      |
| `max_count` | `1`                                       | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/props/physics/chain_torch_ghostly.xml` | Path to the entity XML file.              |

### `g_ghostlamp`

Identical to `g_lamp`, likely a legacy or alternative naming.

### `g_candles`

Defines a set of three different candle types with equal probability.

| Attribute   | Value                                | Description                               |
| :---------- | :----------------------------------- | :---------------------------------------- |
| `prob`      | `0.33`                               | Probability for each candle type.         |
| `min_count` | `1`                                  | Minimum number of entities to spawn.      |
| `max_count` | `1`                                  | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/props/physics_candle_X.xml` | Path to the candle entity XML files.      |

### `g_props`

A diverse collection of props including candles, bones, and skulls.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `prob`      | Varies (e.g., `0.33`, `0.6`, `1.5`)       | Probability of spawning each prop.        |
| `min_count` | `1`                                       | Minimum number of entities to spawn.      |
| `max_count` | `1`                                       | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/props/...`                 | Paths to various prop entity XML files.   |
| `offset_y`  | `0` (for skulls)                          | Vertical offset for spawning.             |

### `g_floor_rubble`

Defines various types of floor rubble with different probabilities. Includes dynamic, small, and directional variants.

| Attribute       | Value                                           | Description                                     |
| :-------------- | :---------------------------------------------- | :---------------------------------------------- |
| `prob`          | Varies (e.g., `15.0`, `1.0`, `0.05`)            | Probability of spawning each rubble type.       |
| `material_file` | `data/biome_impl/wandcave/floor_rubble_....png` | Path to the material texture file.              |
| `visual_file`   | `data/biome_impl/wandcave/floor_rubble_....png` | Path to the visual texture file.                |
| `is_unique`     | `0`                                             | Indicates if the rubble is unique (0 = no).     |

*Note: `g_floor_rubble_l` and `g_floor_rubble_r` are specialized versions for left and right-oriented rubble.*

## Spawn Functions

These functions are the actual implementations called by the game to spawn specific content.

### `spawn_ok( x, y )`

A simple helper function to check if a spawn position is within acceptable world boundaries.

### `spawn_items( pos_x, pos_y )`

A placeholder function that appears to have logic for spawning items, including a potential wand altar.

### Specific Entity Spawners

These functions are directly registered with `RegisterSpawnFunction` and handle the spawning of unique biome elements.

*   **`spawn_boss(x, y)`**: Spawns the biome boss and a hint background sprite.
*   **`spawn_boss_phase2_marker(x, y)`**: Spawns a marker for the boss's second phase and a related background sprite.
*   **`spawn_potion_mimic_empty(x, y)`**: Spawns an empty potion mimic, ensuring it's not initially awoken.
*   **`spawn_potion_mimic(x, y)`**: Spawns a standard potion mimic item.
*   **`spawn_puzzle_watchtower(x, y)`**: Spawns a watchtower puzzle element and its hint background.
*   **`spawn_puzzle_darkness(x, y)`**: Spawns a darkness puzzle and associated hint backgrounds.
*   **`spawn_puzzle_potion_mimics(x, y)`**: Spawns a potion mimic puzzle and its hint background.
*   **`spawn_puzzle_barren(x, y)`**: Spawns a barren puzzle and its hint background.
*   **`spawn_sign_left(x, y)`**: Loads a left-facing sign using `LoadPixelScene`.
*   **`spawn_sign_right(x, y)`**: Loads a right-facing sign using `LoadPixelScene`.
*   **`spawn_fish_many(x, y)`**: Spawns a cluster of fish entities.
*   **`spawn_book_barren(x, y)`**: Spawns a barren book.
*   **`spawn_potion_beer(x, y)`**: Spawns a beer potion.
*   **`spawn_potion_milk(x, y)`**: Spawns a milk potion.
*   **`spawn_scorpion(x, y)`**: Spawns a scorpion enemy.

### Generic Spawners

These functions utilize the predefined entity groups for more general spawning.

*   **`spawn_lamp(x, y)`**: Spawns from the `g_lamp` group.
*   **`spawn_props(x, y)`**: Spawns from the `g_props` group.
*   **`spawn_cloud_trap(x, y)`**: Spawns from the `g_cloud_trap` group.
*   **`load_floor_rubble(x, y)`**: Loads random floor rubble from `g_floor_rubble`.
*   **`load_floor_rubble_l(x, y)`**: Loads random left floor rubble from `g_floor_rubble_l`.
*   **`load_floor_rubble_r(x, y)`**: Loads random right floor rubble from `g_floor_rubble_r`.

## Unused/Placeholder Functions

The following functions are defined but appear to be unused or serve as placeholders within this script.

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
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