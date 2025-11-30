---
title: Rainforest Biome Script
category: scripts
---

# Rainforest Biome Script

This script defines the entities and behaviors specific to the Rainforest biome in Noita. It handles enemy spawns, item placement, environmental props, and unique biome features.

## Core Functionality

The script registers several spawn functions that are called by the game's director system at specific points or under certain conditions.

### Registered Spawn Functions

| Function Name        | Trigger Condition (Color ID) | Description                                    |
| :------------------- | :--------------------------- | :--------------------------------------------- |
| `init`               | `0xffffeedd`                 | Initializes biome-specific elements (e.g., portal) |
| `spawn_scavengers`   | `0xff400000`                 | Spawns scavenger-type enemies.                  |
| `spawn_large_enemies`| `0xff400080`                 | Spawns larger, more formidable enemies.        |
| `spawn_lamp2`        | `0xffC8C800`                 | Spawns a specific type of lamp.                |
| `load_pixel_scene4`  | `0xff00AC64`                 | Loads a specific pixel scene for the biome.    |
| `spawn_vines`        | `0xff80FF5A`                 | Spawns vine structures.                        |
| `spawn_dragonspot`   | `0xff943030`                 | Spawns a dragon-related entity.                |
| `spawn_root_grower`  | `0xff4c63e0`                 | Spawns a root-growing entity.                  |
| `spawn_tree`         | `0xff806326`                 | Spawns tree structures.                        |

## Enemy Spawning Tables

These tables define the probability and count of various enemies that can spawn within the Rainforest biome.

### `g_small_enemies`

This table governs the spawning of smaller, more common enemies.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this enemy group spawning.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |
| `entities`  | A list of entities to choose from when this entry is selected.           |

**Key Entities:**

*   `data/entities/animals/rainforest/fly.xml`
*   `data/entities/animals/lukki/lukki_longleg.xml`
*   `data/entities/animals/rainforest/shooterflower.xml`
*   `data/entities/animals/rainforest/scavenger_poison.xml`
*   `data/entities/projectiles/mine.xml`
*   `data/entities/animals/rainforest/bloom.xml`

### `g_big_enemies`

This table defines the spawning of larger and more dangerous enemies.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this enemy group spawning.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |
| `entities`  | A list of entities to choose from when this entry is selected.           |
| `ngpluslevel` | Minimum New Game Plus level required for this entity to spawn.         |

**Key Entities:**

*   `data/entities/animals/rainforest/fungus.xml`
*   `data/entities/animals/rainforest/bloom.xml`
*   `data/entities/animals/rainforest/scavenger_mine.xml`
*   `data/entities/animals/rainforest/shooterflower.xml`
*   `data/entities/animals/spearbot.xml`
*   `data/entities/animals/wizard_hearty.xml`

### `g_large_enemies`

This table specifically handles the spawning of large enemies, distinct from `g_big_enemies`.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this enemy group spawning.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |
| `entities`  | A list of entities to choose from when this entry is selected.           |

**Key Entities:**

*   `data/entities/animals/rainforest/shooterflower.xml`
*   `data/entities/animals/rainforest/fungus.xml`
*   `data/entities/animals/rainforest/bloom.xml`
*   `data/entities/animals/lukki/lukki_longleg.xml`
*   `data/entities/animals/rainforest/scavenger_leader.xml`
*   `data/entities/projectiles/mine.xml`

### `g_scavengers`

This table defines the types and probabilities of scavenger enemies.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this enemy group spawning.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |
| `entities`  | A list of entities to choose from when this entry is selected.           |

**Key Entities:**

*   `data/entities/animals/rainforest/scavenger_smg.xml`
*   `data/entities/animals/rainforest/scavenger_grenade.xml`
*   `data/entities/animals/rainforest/flamer.xml`
*   `data/entities/animals/rainforest/sniper.xml`
*   `data/entities/animals/rainforest/scavenger_leader.xml`
*   `data/entities/projectiles/mine.xml`

## Unique Enemy Spawns

These tables define specific, less common enemy spawns.

### `g_unique_enemy`

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this enemy group spawning.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |

**Key Entities:**

*   `data/entities/buildings/physics_cocoon.xml`
*   `data/entities/projectiles/mine.xml`
*   `data/entities/animals/rainforest/shooterflower.xml`

### `g_unique_enemy2`

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this enemy group spawning.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |

**Key Entities:**

*   `data/entities/buildings/lukki_eggs.xml`

## Item Spawning

### `g_items`

This table defines the probability of various wands and items spawning.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this item group spawning.                                 |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |

**Key Entities:**

*   `data/entities/items/wand_level_04.xml`
*   `data/entities/items/wand_level_05.xml`
*   `data/entities/items/wand_unshuffle_02.xml`
*   `data/entities/items/wand_level_04_better.xml`

## Environmental Props and Structures

### `g_nest`

Spawns various types of nests.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this nest type spawning.                                  |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |

**Key Entities:**

*   `data/entities/buildings/flynest.xml`
*   `data/entities/buildings/spidernest.xml`

### `g_props`

Spawns various interactive props.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this prop type spawning.                                  |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |
| `offset_y`  | Vertical offset for spawning.                                            |

**Key Entities:**

*   `data/entities/props/physics_barrel_radioactive.xml`
*   `data/entities/props/physics_barrel_oil.xml`
*   `data/entities/props/physics_box_explosive.xml`
*   `data/entities/projectiles/mine.xml`
*   `data/entities/props/physics_seamine.xml`

### `g_lamp` and `g_lamp2`

These tables define different types of lamps that can spawn.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this lamp type spawning.                                  |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |

**Key Entities:**

*   `data/entities/props/physics_torch_stand.xml`
*   `data/entities/props/physics_tubelamp.xml`

### `g_ghostlamp`

Spawns a specific ghostly lamp.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this lamp type spawning.                                  |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |
| `offset_y`  | Vertical offset for spawning.                                            |

**Key Entities:**

*   `data/entities/props/physics_chain_torch_ghostly.xml`

### `g_candles`

Spawns various types of candles.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this candle type spawning.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |

**Key Entities:**

*   `data/entities/props/physics_candle_1.xml`
*   `data/entities/props/physics_candle_2.xml`
*   `data/entities/props/physics_candle_3.xml`

### `g_vines`

Spawns different lengths and types of vines.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this vine type spawning.                                  |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |

**Key Entities:**

*   `data/entities/verlet_chains/vines/verlet_vine.xml`
*   `data/entities/verlet_chains/vines/verlet_vine_long.xml`
*   `data/entities/verlet_chains/root/hanging_root_random.xml`

### `g_trees`

Spawns various types of rainforest trees.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this tree type spawning.                                  |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file.                                           |
| `offset_x`  | Horizontal offset for spawning.                                          |
| `offset_y`  | Vertical offset for spawning.                                            |

**Key Entities:**

*   `data/entities/props/rainforest_tree_01.xml`
*   `data/entities/props/rainforest_tree_02.xml`
*   `data/entities/props/rainforest_tree_03.xml`
*   `data/entities/props/rainforest_tree_04.xml`
*   `data/entities/props/rainforest_tree_05.xml`
*   `data/entities/props/rainforest_tree_06.xml`

## Pixel Scenes

These tables define different visual elements and structures that can be loaded as pixel scenes.

### `g_pixel_scene_01`

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `prob`          | Probability of this scene element spawning.                              |
| `material_file` | Path to the material PNG file.                                           |
| `visual_file`   | Path to the visual PNG file.                                             |
| `background_file`| Path to the background PNG file.                                         |
| `is_unique`     | Flag indicating if the scene element is unique.                          |

**Key Scenes:**

*   `data/biome_impl/rainforest/pit01.png`
*   `data/biome_impl/rainforest/oiltank_01.png`

### `g_pixel_scene_02`

| Attribute       | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`          | Probability of this scene element spawning.                              |
| `material_file` | Path to the material PNG file.                                           |
| `visual_file`   | Path to the visual PNG file.                                             |
| `background_file`| Path to the background PNG file.                                         |
| `is_unique`     | Flag indicating if the scene element is unique.                          |

**Key Scenes:**

*   `data/biome_impl/rainforest/hut01.png`
*   `data/biome_impl/rainforest/base.png`
*   `data/biome_impl/rainforest/symbolroom.png`

### `g_pixel_scene_04`

| Attribute       | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`          | Probability of this scene element spawning.                              |
| `material_file` | Path to the material PNG file.                                           |
| `visual_file`   | Path to the visual PNG file.                                             |
| `background_file`| Path to the background PNG file.                                         |
| `is_unique`     | Flag indicating if the scene element is unique.                          |

**Key Scenes:**

*   `data/biome_impl/rainforest/plantlife.png` (with various background files)

## Biome Initialization (`init` function)

The `init` function is responsible for setting up biome-specific elements, including the portal and hint statues.

### Key Elements:

*   **Portal Target:** Spawns a `summon_portal_target.xml` entity at a calculated position.
*   **Hint Statues:** Spawns two types of statues (`rainforest_statue_01.png` and `rainforest_statue_02.png`) on the biome's rim, oriented to point towards the portal spawn location. These statues are placed using raycasting to ensure they are grounded.
*   **Biome Boundaries:** Defines `biome_x_min`, `biome_x_max`, `biome_y_min`, and `biome_y_max` to determine the area where the portal and statues can spawn.

## Helper Functions

The script utilizes several helper functions for spawning and loading:

*   `RegisterSpawnFunction`: Registers functions to be called by the game director.
*   `dofile_once`: Includes other Lua files.
*   `spawn`: A generic function to spawn entities based on probability tables.
*   `LoadPixelScene`: Loads a specific pixel scene.
*   `load_random_pixel_scene`: Loads a random pixel scene from a given table.
*   `EntityLoad`: Loads a specific entity at given coordinates.
*   `get_portal_position`: Retrieves the calculated portal spawn position.
*   `RaytracePlatforms`: Performs raycasting to find ground surfaces.
*   `ProceduralRandomi`, `ProceduralRandomf`, `ProceduralRandom`: Generates pseudo-random numbers for varied spawning.