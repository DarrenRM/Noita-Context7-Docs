---
title: Coalmine Alternative Biome Script
category: scripts
---

---

# Coalmine Alternative Biome Script

This script defines the alternative biome configuration for the Coalmine in Noita. It specifies the entities, props, and pixel scenes that can spawn within this biome, along with their probabilities and spawn conditions.

## Core Biome Functions

This section outlines the default functions called by the biome generator.

- `CHEST_LEVEL`: Defines the level of action IDs spawned from chests.
- `dofile_once`: Includes essential helper scripts for biome generation and item spawning.
- `RegisterSpawnFunction`: Registers specific functions to be called based on color IDs found in the biome's material files.

### Registered Spawn Functions

| Color ID | Function Name     | Description                               |
| :------- | :---------------- | :---------------------------------------- |
| `0xff0000ff` | `spawn_nest`      | Spawns nests.                             |
| `0xffB40000` | `spawn_fungi`     | Spawns fungi.                             |
| `0xff969678` | `load_structures` | Loads biome-specific structures.          |
| `0xff967878` | `load_large_structures` | Loads larger biome-specific structures. |
| `0xff80FF5A` | `spawn_vines`     | Spawns vines.                             |
| `0xff33934c` | `spawn_shopitem`  | Spawns shop items.                        |

## Enemy Spawning Tables

These tables define the probabilities and types of enemies that can spawn in the Coalmine alternative biome.

### `g_small_enemies`

Defines the pool of smaller enemies that can spawn.

| Attribute   | Value                                     | Description                                                              |
| :---------- | :---------------------------------------- | :----------------------------------------------------------------------- |
| `prob`      | `1.0`                                     | Probability of spawning.                                                 |
| `min_count` | `0`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `0`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `""`                                      | Entity path (empty for no spawn).                                        |
| `prob`      | `0.4`                                     | Probability of spawning.                                                 |
| `min_count` | `1`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `2`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/zombie.xml`        | Entity path for Zombie.                                                  |
| `prob`      | `0.1`                                     | Probability of spawning.                                                 |
| `min_count` | `1`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/slimeshooter.xml`  | Entity path for Slimeshooter.                                            |
| `prob`      | `0.2`                                     | Probability of spawning.                                                 |
| `min_count` | `1`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `3`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/frog.xml`          | Entity path for Frog.                                                    |
| `prob`      | `0.3`                                     | Probability of spawning.                                                 |
| `min_count` | `2`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `2`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/miner_weak.xml`    | Entity path for Weak Miner.                                              |
| `prob`      | `0.1`                                     | Probability of spawning.                                                 |
| `min_count` | `2`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `2`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/miner_fire.xml`    | Entity path for Fire Miner.                                              |
| `prob`      | `0.1`                                     | Probability of spawning.                                                 |
| `min_count` | `1`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/shotgunner.xml`    | Entity path for Shotgunner.                                              |
| `prob`      | `0.1`                                     | Probability of spawning.                                                 |
| `min_count` | `1`                                       | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                       | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/wizard_dark.xml`   | Entity path for Dark Wizard.                                             |
| `ngpluslevel` | `1`                                       | Minimum New Game+ level for this enemy to spawn.                         |

### `g_big_enemies`

Defines the pool of larger enemies that can spawn.

| Attribute   | Value                                           | Description                                                              |
| :---------- | :---------------------------------------------- | :----------------------------------------------------------------------- |
| `prob`      | `1.7`                                           | Probability of spawning.                                                 |
| `min_count` | `0`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `0`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `""`                                            | Entity path (empty for no spawn).                                        |
| `prob`      | `0.2`                                           | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/firemage_weak.xml`       | Entity path for Weak Fire Mage.                                          |
| `prob`      | `0.01`                                          | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/worm.xml`                | Entity path for Worm.                                                    |
| `prob`      | `0.1`                                           | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entities`  | `["data/entities/animals/miner.xml", ...]`      | List of entities to spawn (e.g., multiple miners and a shotgunner).      |
| `prob`      | `0.12`                                          | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/shotgunner.xml`          | Entity path for Shotgunner.                                              |
| `prob`      | `0.1`                                           | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/acidshooter.xml`        | Entity path for Acid Shooter.                                            |
| `prob`      | `0.08`                                          | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/giantshooter.xml`        | Entity path for Giant Shooter.                                           |
| `prob`      | `0.09`                                          | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/fireskull.xml`           | Entity path for Fire Skull.                                              |
| `prob`      | `0.2`                                           | Probability of spawning.                                                 |
| `min_count` | `3`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `5`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/frog.xml`                | Entity path for Frog.                                                    |
| `prob`      | `0.13`                                          | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/frog_big.xml`            | Entity path for Big Frog.                                                |
| `prob`      | `0.05`                                          | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entities`  | `["data/entities/animals/frog.xml", ...]`       | List of entities to spawn (e.g., frogs and a big frog).                  |
| `prob`      | `0.3`                                           | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `2`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/miner_santa.xml`         | Entity path for Santa Miner.                                             |
| `spawn_check` | `function() ... end`                          | Custom function to check spawn conditions (e.g., Christmas season).      |
| `prob`      | `0.1`                                           | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/shaman.xml`              | Entity path for Shaman.                                                  |
| `prob`      | `0.02`                                          | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/drone_shield.xml`        | Entity path for Shield Drone.                                            |
| `ngpluslevel` | `2`                                             | Minimum New Game+ level for this enemy to spawn.                         |
| `prob`      | `0.1`                                           | Probability of spawning.                                                 |
| `min_count` | `1`                                             | Minimum number of enemies to spawn.                                      |
| `max_count` | `1`                                             | Maximum number of enemies to spawn.                                      |
| `entity`    | `data/entities/animals/scavenger_clusterbomb.xml` | Entity path for Cluster Bomb Scavenger.                                  |
| `ngpluslevel` | `1`                                             | Minimum New Game+ level for this enemy to spawn.                         |

### `g_lamp`

Defines the probability of spawning lamps.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `prob`      | `0.7`                                     | Probability of spawning.                  |
| `min_count` | `1`                                       | Minimum number of lamps to spawn.         |
| `max_count` | `1`                                       | Maximum number of lamps to spawn.         |
| `entity`    | `data/entities/props/physics/lantern_small.xml` | Entity path for a small lantern.          |
| `prob`      | `0.3`                                     | Probability of spawning.                  |
| `min_count` | `1`                                       | Minimum number of lamps to spawn.         |
| `max_count` | `1`                                       | Maximum number of lamps to spawn.         |
| `entity`    | `""`                                      | Entity path (empty for no spawn).         |

### `g_unique_enemy`, `g_unique_enemy2`, `g_unique_enemy3`

These tables define specific unique enemy encounters with their own spawn probabilities and conditions. `g_unique_enemy2` includes a Christmas-themed spawn condition for Santa Miners.

### `g_fungi`

Defines the probability of spawning fungi.

| Attribute   | Value                                 | Description                               |
| :---------- | :------------------------------------ | :---------------------------------------- |
| `prob`      | `0.5`                                 | Probability of spawning.                  |
| `min_count` | `1`                                   | Minimum number of fungi to spawn.         |
| `max_count` | `1`                                   | Maximum number of fungi to spawn.         |
| `entity`    | `data/entities/animals/fungus.xml`    | Entity path for Fungus.                   |

## Item Spawning

### `g_items`

Defines the pool of wands that can spawn.

| Attribute   | Value                                         | Description                               |
| :---------- | :-------------------------------------------- | :---------------------------------------- |
| `prob`      | `1`                                           | Probability of spawning.                  |
| `min_count` | `1`                                           | Minimum number of wands to spawn.         |
| `max_count` | `1`                                           | Maximum number of wands to spawn.         |
| `entity`    | `data/entities/items/wands/level_01/wand_001.xml` | Entity path for Wand 001.                 |
| ...         | ...                                           | ...                                       |
| `entity`    | `data/entities/items/wands/level_01/wand_009.xml` | Entity path for Wand 009.                 |

## Prop and Structure Spawning

### `g_props`, `g_props2`, `g_props3`

These tables define various props and interactive objects that can spawn, including explosive boxes, minecarts, and different types of barrels.

### `g_structures`, `g_large_structures`

These tables define the biome-specific structures that can be placed within the Coalmine.

### `g_ghostlamp`

Defines the spawning of ghostly torches.

| Attribute   | Value                                           | Description                               |
| :---------- | :---------------------------------------------- | :---------------------------------------- |
| `prob`      | `1.0`                                           | Probability of spawning.                  |
| `min_count` | `1`                                             | Minimum number of ghost lamps to spawn.   |
| `max_count` | `1`                                             | Maximum number of ghost lamps to spawn.   |
| `entity`    | `data/entities/props/physics/chain_torch_ghostly.xml` | Entity path for a ghostly chain torch.    |

### `g_candles`

Defines the spawning of different types of candles.

| Attribute   | Value                                 | Description                               |
| :---------- | :------------------------------------ | :---------------------------------------- |
| `prob`      | `0.33`                                | Probability of spawning.                  |
| `min_count` | `1`                                   | Minimum number of candles to spawn.       |
| `max_count` | `1`                                   | Maximum number of candles to spawn.       |
| `entity`    | `data/entities/props/physics_candle_1.xml` | Entity path for Candle 1.                 |
| ...         | ...                                   | ...                                       |
| `entity`    | `data/entities/props/physics_candle_3.xml` | Entity path for Candle 3.                 |

### `g_nest`

Defines the spawning of fly nests.

| Attribute   | Value                                 | Description                               |
| :---------- | :------------------------------------ | :---------------------------------------- |
| `prob`      | `0.5`                                 | Probability of spawning.                  |
| `min_count` | `1`                                   | Minimum number of nests to spawn.         |
| `max_count` | `1`                                   | Maximum number of nests to spawn.         |
| `entity`    | `data/entities/buildings/flynest.xml` | Entity path for Fly Nest.                 |

## Pixel Scene Definitions

### `g_pixel_scene_01`, `g_pixel_scene_02`

These tables define various pre-designed "pixel scenes" that can be loaded into the biome. They include material, visual, and background files, along with a flag for uniqueness.

| Attribute       | Value                                            | Description                                                              |
| :-------------- | :----------------------------------------------- | :----------------------------------------------------------------------- |
| `prob`          | `0.5`                                            | Probability of this scene spawning.                                      |
| `material_file` | `data/biome_impl/coalmine/coalpit01.png`         | Path to the material definition file for the scene.                      |
| `visual_file`   | `data/biome_impl/coalmine/coalpit01_visual.png`  | Path to the visual definition file for the scene.                        |
| `background_file` | `""`                                             | Path to the background file (if any).                                    |
| `is_unique`     | `0`                                              | Flag indicating if the scene is unique (0 for not unique, 1 for unique). |
| `prob`          | `1.2`                                            | Probability of this scene spawning.                                      |
| `material_file` | `data/biome_impl/coalmine/symbolroom_alt.png`    | Path to the material definition file for the scene.                      |
| `visual_file`   | `""`                                             | Path to the visual definition file (if any).                             |
| `background_file` | `""`                                             | Path to the background file (if any).                                    |
| `is_unique`     | `0`                                              | Flag indicating if the scene is unique.                                  |

### `g_vines`

Defines the spawning of different lengths of vines.

| Attribute   | Value                                           | Description                               |
| :---------- | :---------------------------------------------- | :---------------------------------------- |
| `prob`      | `0.4`                                           | Probability of spawning.                  |
| `min_count` | `1`                                             | Minimum number of vines to spawn.         |
| `max_count` | `1`                                             | Maximum number of vines to spawn.         |
| `entity`    | `data/entities/verlet_chains/vines/verlet_vine.xml` | Entity path for a standard vine.          |
| `prob`      | `1.5`                                           | Probability of spawning.                  |
| `min_count` | `1`                                             | Minimum number of vines to spawn.         |
| `max_count` | `1`                                             | Maximum number of vines to spawn.         |
| `entity`    | `""`                                            | Entity path (empty for no spawn).         |

## Spawn Functions

These functions are called by the game engine to populate the biome with entities and structures.

### `spawn_items(pos_x, pos_y)`

A special function for spawning items within the Coalmine, with a chance to load a wand altar.

### `spawn_small_enemies(x, y)`

Spawns small enemies using the `g_small_enemies` table.

### `spawn_big_enemies(x, y)`

Spawns big enemies using the `g_big_enemies` table.

### `spawn_lamp(x, y)`

Spawns lamps using the `g_lamp` table.

### `spawn_ghostlamp(x, y)`

Spawns ghostly lamps using the `g_ghostlamp` table.

### `spawn_props(x, y)`

Spawns props using the `g_props` table.

### `spawn_props2(x, y)`

Spawns props using the `g_props2` table.

### `spawn_props3(x, y)`

Spawns props using the `g_props3` table.

### `spawn_unique_enemy(x, y)`

Spawns unique enemies using the `g_unique_enemy` table.

### `spawn_unique_enemy2(x, y)`

Spawns unique enemies using the `g_unique_enemy2` table.

### `spawn_unique_enemy3(x, y)`

Spawns unique enemies using the `g_unique_enemy3` table.

### `load_pixel_scene(x, y)`

Loads a random pixel scene from `g_pixel_scene_01`.

### `load_pixel_scene2(x, y)`

Loads a random pixel scene from `g_pixel_scene_02`.

### `load_structures(x, y)`

Loads biome-specific structures using the `g_structures` table.

### `load_large_structures(x, y)`

Loads larger biome-specific structures using the `g_large_structures` table.

### `spawn_nest(x, y)`

Spawns nests using the `g_nest` table.

### `spawn_fungi(x, y)`

Spawns fungi using the `g_fungi` table.

### `spawn_vines(x, y)`

Spawns vines using the `g_vines` table.

### `spawn_shopitem(x, y)`

Generates a shop item at the specified location.