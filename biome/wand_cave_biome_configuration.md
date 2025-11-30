---
title: Wand Cave Biome Configuration
category: biome/
---

# Wand Cave Biome Configuration

This document details the configuration for the Wand Cave biome in Noita, focusing on the entities and environmental elements that can spawn within it.

## Core Biome Functions

The script registers several functions to handle the spawning of specific biome elements. These are typically called by the game's director system.

### Registered Spawn Functions

| Color ID   | Function Name       | Description                                     |
| :--------- | :------------------ | :---------------------------------------------- |
| `0xff805000` | `spawn_cloud_trap`  | Spawns a cloud trap entity.                     |
| `0xff397780` | `load_floor_rubble` | Loads a random floor rubble configuration.      |
| `0xff00ffa0` | `load_floor_rubble_l` | Loads a specific left-side floor rubble.        |
| `0xff1ca7ff` | `load_floor_rubble_r` | Loads a specific right-side floor rubble.       |

## Entity Spawning Tables

These tables define the probabilities and types of entities that can spawn in the Wand Cave.

### `g_small_enemies`

Configuration for spawning smaller enemy types.

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                 | Total probability sum (calculated dynamically). |
| `prob`      | `0.3`                               | Probability of spawning nothing (air).          |
| `min_count` | `0`                                 | Minimum enemies to spawn.                       |
| `max_count` | `0`                                 | Maximum enemies to spawn.                       |
| `entity`    | `""`                                | No entity spawned for this entry.               |
| `prob`      | `0.1`                               | Probability of spawning `wand_ghost`.           |
| `min_count` | `1`                                 | Minimum `wand_ghost` to spawn.                  |
| `max_count` | `2`                                 | Maximum `wand_ghost` to spawn.                  |
| `entity`    | `"data/entities/animals/wand_ghost.xml"` | Entity to spawn.                                |

### `g_big_enemies`

Configuration for spawning larger and more dangerous enemy types.

| Attribute   | Value                                       | Description                                     |
| :---------- | :------------------------------------------ | :---------------------------------------------- |
| `total_prob`| `0`                                         | Total probability sum (calculated dynamically). |
| `prob`      | `0.3`                                       | Probability of spawning nothing (air).          |
| `min_count` | `0`                                         | Minimum enemies to spawn.                       |
| `max_count` | `0`                                         | Maximum enemies to spawn.                       |
| `entity`    | `""`                                        | No entity spawned for this entry.               |
| `prob`      | `0.1`                                       | Probability of spawning `statue_physics`.       |
| `min_count` | `1`                                         | Minimum `statue_physics` to spawn.              |
| `max_count` | `1`                                         | Maximum `statue_physics` to spawn.              |
| `entity`    | `"data/entities/animals/statue_physics.xml"`| Entity to spawn.                                |
| `prob`      | `0.2`                                       | Probability of spawning `phantom_a`.            |
| `entity`    | `"data/entities/animals/phantom_a.xml"`     | Entity to spawn.                                |
| `prob`      | `0.2`                                       | Probability of spawning `phantom_b`.            |
| `entity`    | `"data/entities/animals/phantom_b.xml"`     | Entity to spawn.                                |
| `prob`      | `0.09`                                      | Probability of spawning `necromancer`.          |
| `entity`    | `"data/entities/animals/necromancer.xml"`   | Entity to spawn.                                |
| `prob`      | `0.09`                                      | Probability of spawning `wizard_returner`.      |
| `entity`    | `"data/entities/animals/wizard_returner.xml"`| Entity to spawn.                                |
| `prob`      | `0.08`                                      | Probability of spawning `wizard_neutral`.       |
| `entity`    | `"data/entities/animals/wizard_neutral.xml"`| Entity to spawn.                                |
| `prob`      | `0.04`                                      | Probability of spawning `wizard_hearty`.        |
| `entity`    | `"data/entities/animals/wizard_hearty.xml"` | Entity to spawn.                                |
| `prob`      | `0.01`                                      | Probability of spawning `wraith_glowing`.       |
| `entity`    | `"data/entities/animals/wraith_glowing.xml"`| Entity to spawn.                                |
| `prob`      | `0.02`                                      | Probability of spawning `enlightened_alchemist`.|
| `entity`    | `"data/entities/animals/enlightened_alchemist.xml"` | Entity to spawn.                                |
| `prob`      | `0.02`                                      | Probability of spawning `failed_alchemist`.     |
| `entity`    | `"data/entities/animals/failed_alchemist.xml"`| Entity to spawn.                                |
| `prob`      | `0.01`                                      | Probability of spawning `weakspirit`.           |
| `ngpluslevel`| `1`                                         | Only spawns in New Game Plus level 1 or higher. |
| `entity`    | `"data/entities/animals/weakspirit.xml"`    | Entity to spawn.                                |

### `g_lamp`

Configuration for spawning lamps.

| Attribute   | Value                                       | Description                                     |
| :---------- | :------------------------------------------ | :---------------------------------------------- |
| `total_prob`| `0`                                         | Total probability sum (calculated dynamically). |
| `prob`      | `1.0`                                       | Probability of spawning `chain_torch_ghostly`.  |
| `min_count` | `1`                                         | Minimum lamps to spawn.                         |
| `max_count` | `1`                                         | Maximum lamps to spawn.                         |
| `entity`    | `"data/entities/props/physics/chain_torch_ghostly.xml"` | Entity to spawn.                                |

### `g_ghostlamp`

Configuration for spawning ghost lamps (identical to `g_lamp`).

| Attribute   | Value                                       | Description                                     |
| :---------- | :------------------------------------------ | :---------------------------------------------- |
| `total_prob`| `0`                                         | Total probability sum (calculated dynamically). |
| `prob`      | `1.0`                                       | Probability of spawning `chain_torch_ghostly`.  |
| `min_count` | `1`                                         | Minimum ghost lamps to spawn.                   |
| `max_count` | `1`                                         | Maximum ghost lamps to spawn.                   |
| `entity`    | `"data/entities/props/physics/chain_torch_ghostly.xml"` | Entity to spawn.                                |

### `g_candles`

Configuration for spawning various types of candles.

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                 | Total probability sum (calculated dynamically). |
| `prob`      | `0.33`                              | Probability of spawning `physics_candle_1`.     |
| `min_count` | `1`                                 | Minimum candles to spawn.                       |
| `max_count` | `1`                                 | Maximum candles to spawn.                       |
| `entity`    | `"data/entities/props/physics_candle_1.xml"` | Entity to spawn.                                |
| `prob`      | `0.33`                              | Probability of spawning `physics_candle_2`.     |
| `entity`    | `"data/entities/props/physics_candle_2.xml"` | Entity to spawn.                                |
| `prob`      | `0.33`                              | Probability of spawning `physics_candle_3`.     |
| `entity`    | `"data/entities/props/physics_candle_3.xml"` | Entity to spawn.                                |

### `g_props`

Configuration for spawning various props, including candles and bones.

| Attribute   | Value                                   | Description                                     |
| :---------- | :-------------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                     | Total probability sum (calculated dynamically). |
| `prob`      | `0.33`                                  | Probability of spawning `physics_candle_1`.     |
| `min_count` | `1`                                     | Minimum props to spawn.                         |
| `max_count` | `1`                                     | Maximum props to spawn.                         |
| `entity`    | `"data/entities/props/physics_candle_1.xml"` | Entity to spawn.                                |
| `prob`      | `0.33`                                  | Probability of spawning `physics_candle_2`.     |
| `entity`    | `"data/entities/props/physics_candle_2.xml"` | Entity to spawn.                                |
| `prob`      | `0.33`                                  | Probability of spawning `physics_candle_3`.     |
| `entity`    | `"data/entities/props/physics_candle_3.xml"` | Entity to spawn.                                |
| `prob`      | `5.4`                                   | Probability of spawning nothing (air).          |
| `entity`    | `""`                                    | No entity spawned for this entry.               |
| `prob`      | `0.6`                                   | Probability of spawning `physics_bone_01`.      |
| `entity`    | `"data/entities/props/physics_bone_01.xml"` | Entity to spawn.                                |
| `prob`      | `0.6`                                   | Probability of spawning `physics_bone_02`.      |
| `entity`    | `"data/entities/props/physics_bone_02.xml"` | Entity to spawn.                                |
| `prob`      | `0.6`                                   | Probability of spawning `physics_bone_03`.      |
| `entity`    | `"data/entities/props/physics_bone_03.xml"` | Entity to spawn.                                |
| `prob`      | `0.6`                                   | Probability of spawning `physics_bone_04`.      |
| `entity`    | `"data/entities/props/physics_bone_04.xml"` | Entity to spawn.                                |
| `prob`      | `0.6`                                   | Probability of spawning `physics_bone_05`.      |
| `entity`    | `"data/entities/props/physics_bone_05.xml"` | Entity to spawn.                                |
| `prob`      | `0.6`                                   | Probability of spawning `physics_bone_06`.      |
| `entity`    | `"data/entities/props/physics_bone_06.xml"` | Entity to spawn.                                |
| `prob`      | `1.5`                                   | Probability of spawning `physics_skull_01`.     |
| `offset_y`  | `0`                                     | Vertical offset for spawning.                   |
| `entity`    | `"data/entities/props/physics_skull_01.xml"`| Entity to spawn.                                |
| `prob`      | `1.5`                                   | Probability of spawning `physics_skull_02`.     |
| `entity`    | `"data/entities/props/physics_skull_02.xml"`| Entity to spawn.                                |
| `prob`      | `1.5`                                   | Probability of spawning `physics_skull_03`.     |
| `entity`    | `"data/entities/props/physics_skull_03.xml"`| Entity to spawn.                                |

### `g_cloud_trap`

Configuration for spawning cloud traps.

| Attribute   | Value                                   | Description                                     |
| :---------- | :-------------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                     | Total probability sum (calculated dynamically). |
| `prob`      | `0.2`                                   | Probability of spawning nothing (air).          |
| `min_count` | `0`                                     | Minimum cloud traps to spawn.                   |
| `max_count` | `0`                                     | Maximum cloud traps to spawn.                   |
| `entity`    | `""`                                    | No entity spawned for this entry.               |
| `prob`      | `0.3`                                   | Probability of spawning `cloud_trap`.           |
| `min_count` | `1`                                     | Minimum `cloud_trap` to spawn.                  |
| `max_count` | `1`                                     | Maximum `cloud_trap` to spawn.                  |
| `entity`    | `"data/entities/buildings/cloud_trap.xml"`| Entity to spawn.                                |

### `g_floor_rubble`

Configuration for generic floor rubble variations.

| Attribute       | Value                                                              | Description                                     |
| :-------------- | :----------------------------------------------------------------- | :---------------------------------------------- |
| `total_prob`    | `0`                                                                | Total probability sum (calculated dynamically). |
| `prob`          | `15.0`                                                             | High probability for empty/default rubble.      |
| `material_file` | `""`                                                               | No specific material.                           |
| `visual_file`   | `""`                                                               | No specific visual.                             |
| `background_file`| `""`                                                               | No specific background.                         |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_dynamic_01`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_dynamic_01.png"`           | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_dynamic_01_visual.png"`     | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_dynamic_02`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_dynamic_02.png"`           | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_dynamic_02_visual.png"`     | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.5`                                                              | Probability of spawning `floor_rubble_small_01`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_01.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_01_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.5`                                                              | Probability of spawning `floor_rubble_small_02`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_02.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_02_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.5`                                                              | Probability of spawning `floor_rubble_small_03`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_03.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_03_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.05`                                                             | Probability of spawning `floor_rubble_l_01`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_l_01.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_l_01_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.05`                                                             | Probability of spawning `floor_rubble_l_02`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_l_02.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_l_02_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.05`                                                             | Probability of spawning `floor_rubble_r_01`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_r_01.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_r_01_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.05`                                                             | Probability of spawning `floor_rubble_r_02`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_r_02.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_r_02_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |

### `g_floor_rubble_l`

Configuration for left-specific floor rubble variations.

| Attribute       | Value                                                              | Description                                     |
| :-------------- | :----------------------------------------------------------------- | :---------------------------------------------- |
| `total_prob`    | `0`                                                                | Total probability sum (calculated dynamically). |
| `prob`          | `2.0`                                                              | High probability for empty/default rubble.      |
| `material_file` | `""`                                                               | No specific material.                           |
| `visual_file`   | `""`                                                               | No specific visual.                             |
| `background_file`| `""`                                                               | No specific background.                         |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_l_01`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_l_01.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_l_01_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_l_02`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_l_02.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_l_02_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_small_01`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_01.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_01_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_small_02`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_02.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_02_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_small_03`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_03.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_03_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.5`                                                              | Probability of spawning `floor_rubble_dynamic_01`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_dynamic_01.png"`           | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_dynamic_01_visual.png"`     | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.5`                                                              | Probability of spawning `floor_rubble_dynamic_02`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_dynamic_02.png"`           | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_dynamic_02_visual.png"`     | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |

### `g_floor_rubble_r`

Configuration for right-specific floor rubble variations.

| Attribute       | Value                                                              | Description                                     |
| :-------------- | :----------------------------------------------------------------- | :---------------------------------------------- |
| `total_prob`    | `0`                                                                | Total probability sum (calculated dynamically). |
| `prob`          | `2.0`                                                              | High probability for empty/default rubble.      |
| `material_file` | `""`                                                               | No specific material.                           |
| `visual_file`   | `""`                                                               | No specific visual.                             |
| `background_file`| `""`                                                               | No specific background.                         |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_r_01`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_r_01.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_r_01_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_r_02`.    |
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_r_02.png"`                 | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_r_02_visual.png"`           | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_small_01`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_01.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_01_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_small_02`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_02.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_02_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `1.0`                                                              | Probability of spawning `floor_rubble_small_03`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_small_03.png"`             | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_small_03_visual.png"`       | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.5`                                                              | Probability of spawning `floor_rubble_dynamic_01`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_dynamic_01.png"`           | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_dynamic_01_visual.png"`     | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |
| `prob`          | `0.5`                                                              | Probability of spawning `floor_rubble_dynamic_02`.|
| `material_file` | `"data/biome_impl/wandcave/floor_rubble_dynamic_02.png"`           | Material texture.                               |
| `visual_file`   | `"data/biome_impl/wandcave/floor_rubble_dynamic_02_visual.png"`     | Visual texture.                                 |
| `is_unique`     | `0`                                                                | Not a unique element.                           |

## Specific Spawning Logic

### `spawn_items(pos_x, pos_y)`

This function contains custom logic for spawning items within the Wand Cave, potentially influenced by its unique characteristics.

```lua
-- this is a special function tweaked for spawning things in coal mines
function spawn_items( pos_x, pos_y )
	local r = ProceduralRandom( pos_x, pos_y )
	-- 20% is air, nothing happens
	if( r < 0.47 ) then return end
	r = ProceduralRandom( pos_x-11.431, pos_y+10.5257 )
	
	if( r < 0.725 ) then
	else
		LoadPixelScene( "data/biome_impl/wand_altar.png", "data/biome_impl/wand_altar_visual.png", pos_x-10, pos_y-17, "", true )
		return
	end
end
```

## Helper Functions

These functions are wrappers around the `spawn` and `load_random_pixel_scene` functions, providing convenient ways to trigger specific entity or environment spawns.

### Enemy Spawning

*   `spawn_small_enemies(x, y)`: Spawns entities defined in `g_small_enemies`.
*   `spawn_big_enemies(x, y)`: Spawns entities defined in `g_big_enemies`.

### Prop and Environment Spawning

*   `spawn_lamp(x, y)`: Spawns entities defined in `g_lamp`.
*   `spawn_props(x, y)`: Spawns entities defined in `g_props`.
*   `spawn_cloud_trap(x, y)`: Spawns entities defined in `g_cloud_trap`.
*   `load_floor_rubble(x, y)`: Loads random floor rubble using `g_floor_rubble`.
*   `load_floor_rubble_l(x, y)`: Loads left-specific floor rubble using `g_floor_rubble_l`.
*   `load_floor_rubble_r(x, y)`: Loads right-specific floor rubble using `g_floor_rubble_r`.

## Unused/Placeholder Functions

The following functions are defined but appear to be empty or serve as placeholders, indicating they are not actively used in this script's current implementation.

*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`
*   `spawn_wands( x, y )`