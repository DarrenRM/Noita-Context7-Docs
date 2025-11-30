---
title: Tower Biome Script
category: scripts
---

# Tower Biome Script

This script defines the spawning logic and environmental elements for the "Tower" biome in Noita. It handles the placement of enemies, props, and special structures within this area.

## Core Functionality

The script primarily serves as a configuration file for the Noita game engine, dictating what entities and visual elements should appear in the Tower biome. It relies on several helper functions and pre-defined tables to manage this process.

## Key Spawn Functions

These functions are registered with the game engine and called when specific conditions or biome types are met.

*   **`RegisterSpawnFunction( color, function_name )`**: This is a core Noita function used to associate a specific color (likely representing a tile in the biome's material map) with a Lua function that will be executed when that tile is encountered.

    *   `0xff0000ff` (Red): `spawn_nest` - Spawns enemy nests.
    *   `0xffB40000` (Dark Orange): `spawn_fungi` - Spawns fungal entities.
    *   `0xff80FF5A` (Green): `spawn_vines` - Spawns vine structures.
    *   `0xff55AF8C` (Teal): `spawn_skulls` - Spawns skull-related entities.
    *   `0xff55FF8C` (Light Blue): `spawn_chest` - Spawns chests.
    *   `0xff33934c` (Dark Cyan): `spawn_shopitem` - Spawns shop items.

## Entity Spawning Tables

These tables define the probabilities and types of entities that can be spawned.

### `g_lamp`

Defines the probability of spawning small physics lamps.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `entity`    | Path to the entity XML file.              |

*   **Key Entry**: `data/entities/props/physics_lantern_small.xml` (probability 0.7)

### `g_items`

Defines the probability of spawning various items, primarily wands.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `entity`    | Path to the entity XML file.              |

*   **Key Entries**: Various `wand_level_01` and `wand_00X` entities, all with probability 1.0.

### `g_props`

Defines the probability of spawning various physics props like barrels and skulls.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `offset_y`  | Vertical offset for spawning.             |
| `entity`    | Path to the entity XML file.              |

*   **Key Entries**:
    *   `data/entities/props/physics_box_explosive.xml` (prob 0.5)
    *   `data/entities/props/physics_cart.xml` (prob 0.25)
    *   `data/entities/props/physics_barrel_radioactive.xml` (prob 0.1)
    *   `data/entities/props/physics_barrel_oil.xml` (prob 0.3)
    *   `data/entities/props/physics_skull_0X.xml` (prob 0.1 each)

### `g_props2`

Another group of physics props.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `offset_y`  | Vertical offset for spawning.             |
| `entity`    | Path to the entity XML file.              |

*   **Key Entries**:
    *   `data/entities/props/physics/minecart.xml` (prob 0.2)
    *   `data/entities/props/physics_brewing_stand.xml` (prob 0.5)

### `g_props3`

Spawns potions and other small physics objects.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `offset_y`  | Vertical offset for spawning.             |
| `entity`    | Path to the entity XML file.              |

*   **Key Entry**: `data/entities/items/pickup/potion.xml` (prob 0.3)

### `g_pixel_scene_01` and `g_pixel_scene_02`

These tables define various pre-made pixel scenes (small environmental layouts) that can be loaded into the biome.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `total_prob`     | Total probability for this group.                                        |
| `prob`           | Individual spawn probability.                                            |
| `material_file`  | Path to the material PNG file for the scene.                             |
| `visual_file`    | Path to the visual PNG file for the scene.                               |
| `background_file`| Path to the background PNG file (if any).                                |
| `is_unique`      | Flag indicating if the scene should only spawn once.                     |
| `color_material` | Table mapping specific colors to lists of materials for dynamic generation. |

*   **Key Entries**: Various `coalpit`, `shrine`, `laboratory`, `wandtrap` files, and `oiltank` variations. `wandtrap_h_04` and `wandtrap_h_06` have specific `color_material` configurations for different liquids.

### `g_oiltank` and `g_oiltank_alt`

Specific configurations for oil tank structures, allowing for diverse liquid contents.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `total_prob`     | Total probability for this group.                                        |
| `prob`           | Individual spawn probability.                                            |
| `material_file`  | Path to the material PNG file for the scene.                             |
| `visual_file`    | Path to the visual PNG file for the scene.                               |
| `background_file`| Path to the background PNG file (if any).                                |
| `is_unique`      | Flag indicating if the scene should only spawn once.                     |
| `color_material` | Table mapping specific colors to lists of materials for dynamic generation. |

*   **Key Entries**: Multiple `oiltank` variations with different liquid possibilities, including rare magic liquids.

### `g_i_structures`, `g_structures`, `g_large_structures`

These tables define the spawning of various structural elements within the biome.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `offset_y`  | Vertical offset for spawning.             |
| `entity`    | Path to the entity XML file.              |

*   **Key Entries**: `coalmine_i_structure_0X.xml`, `coalmine_structure_0X.xml`, `coalmine_large_structure_0X.xml`.

### `g_ghostlamp`

Spawns ghostly chain torches.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `offset_y`  | Vertical offset for spawning.             |
| `entity`    | Path to the entity XML file.              |

*   **Key Entry**: `data/entities/props/physics_chain_torch_ghostly.xml` (prob 1.0)

### `g_candles`

Spawns different types of candles.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `entity`    | Path to the entity XML file.              |

*   **Key Entries**: `data/entities/props/physics_candle_1.xml`, `physics_candle_2.xml`, `physics_candle_3.xml` (prob 0.33 each).

### `g_nest`

Defines the spawning of enemy nests.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `entity`    | Path to the entity XML file.              |

*   **Key Entry**: `data/entities/buildings/flynest.xml` (prob 0.5)

### `g_vines`

Defines the spawning of various vine types.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `total_prob`| Total probability for this group.         |
| `prob`      | Individual spawn probability.             |
| `min_count` | Minimum number of entities to spawn.      |
| `max_count` | Maximum number of entities to spawn.      |
| `entity`    | Path to the entity XML file.              |

*   **Key Entries**: `verlet_vine.xml`, `verlet_vine_long.xml`, `verlet_vine_short.xml`, `verlet_vine_shorter.xml`.

## Helper Functions

*   **`safe( x, y )`**: A utility function to check if a given coordinate `(x, y)` falls within a specific "unsafe" region (likely a protected area or a specific biome feature). Returns `true` if safe, `false` otherwise.
*   **`spawn_items( pos_x, pos_y )`**: A specialized function for spawning items, potentially including a `wand_altar` based on procedural randomness.
*   **`spawn_any_enemy( x, y )`**: A generic function to spawn a random enemy from a predefined `enemy_list`. It also applies a damage multiplier to the spawned enemy.
*   **`spawn_small_enemies(x, y, w, h, is_open_path)`**: Calls `spawn_any_enemy`.
*   **`spawn_big_enemies(x, y, w, h, is_open_path)`**: Calls `spawn_any_enemy`.
*   **`spawn_lamp(x, y)`**: Spawns lamps using the `g_lamp` table.
*   **`spawn_props(x, y)`**: Spawns props using the `g_props` table.
*   **`spawn_props2(x, y)`**: Spawns props using the `g_props2` table.
*   **`spawn_props3(x, y)`**: Spawns props using the `g_props3` table.
*   **`spawn_unique_enemy(x, y)`**, **`spawn_unique_enemy2(x, y)`**, **`spawn_unique_enemy3(x, y)`**: These functions currently just call `spawn_any_enemy`, suggesting they might be placeholders or intended for future unique enemy spawning logic.
*   **`spawn_fungi(x, y)`**: Calls `spawn_any_enemy`.
*   **`load_pixel_scene( x, y )`** and **`load_pixel_scene2( x, y )`**: These functions are defined but empty, suggesting they might be intended for future use or are remnants of previous implementations.
*   **`spawn_stash(x,y)`**: An empty function, likely a placeholder.
*   **`spawn_nest(x, y)`**: Calls `spawn_any_enemy`.
*   **`spawn_vines(x, y)`**: Spawns vines using the `g_vines` table.
*   **`spawn_chest(x, y)`**: Spawns either a `chest_random_super` or `chest_random` based on a random chance.
*   **`spawn_skulls(x, y)`**: An empty function.
*   **`spawn_shopitem( x, y )`**: Calls `generate_shop_item` to create a shop item.

## Enemy List (`enemy_list`)

A comprehensive list of enemy entity names that can be spawned by `spawn_any_enemy`. This list includes a wide variety of creatures and entities found throughout Noita.

*   **Key Examples**: `acidshooter`, `alchemist`, `ant`, `assassin`, `barfer`, `bat`, `bigbat`, `firebug`, `fireskull`, `fly`, `frog`, `fungus`, `ghoul`, `miner`, `necromancer`, `rat`, `shooterflower`, `skullfly`, `slimeshooter`, `sniper`, `tank`, `wolf`, `zombie`.
*   Includes some building entities like `buildings/snowcrystal` and `buildings/hpcrystal`.

## `CHEST_LEVEL`

A global variable set to `1`, likely indicating the default level or tier for items spawned from chests.