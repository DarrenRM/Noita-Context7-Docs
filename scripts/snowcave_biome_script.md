---
title: Snowcave Biome Script
category: scripts
---

---

# Snowcave Biome Script

This script defines the entities, props, and special structures that can spawn within the Snowcave biome in Noita. It utilizes a system of probability-based spawning for various elements, including enemies, items, and environmental features.

## Core Functionality

The script primarily registers spawn functions that are called by the game's director system to populate the biome. It also defines several tables that hold the configurations for different spawnable elements.

### Key Spawn Functions

*   `RegisterSpawnFunction( 0xff00AC33, "load_pixel_scene3" )`
*   `RegisterSpawnFunction( 0xff00AC64, "load_pixel_scene4" )`
*   `RegisterSpawnFunction( 0xff55AF4B, "load_altar" )`
*   `RegisterSpawnFunction( 0xff23B9C3, "spawn_altar_torch" )`
*   `RegisterSpawnFunction( 0xff55AF8C, "spawn_skulls" )`
*   `RegisterSpawnFunction( 0xffF516E3, "spawn_scavenger_party" )`
*   `RegisterSpawnFunction( 0xffFFC84E, "spawn_acid" )`
*   `RegisterSpawnFunction( 0xff7285c4, "load_acidtank_right" )`
*   `RegisterSpawnFunction( 0xff9472c4, "load_acidtank_left" )`
*   `RegisterSpawnFunction( 0xff9E8AC2, "load_suspension_bridge" )`

## Enemy Spawning Tables

These tables define the probability and count of various enemies that can spawn in different contexts within the Snowcave.

### `g_small_enemies`

This table governs the spawning of smaller, more common enemies.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this enemy group spawning.                            |
| `min_count` | The minimum number of entities to spawn.                                 |
| `max_count` | The maximum number of entities to spawn.                                 |
| `entity`    | The XML file path for the entity to spawn.                               |
| `entities`  | A table of entities to spawn, allowing for combinations.                 |

**Key Entities:**

*   `data/entities/animals/shotgunner.xml`
*   `data/entities/animals/slimeshooter.xml`
*   `data/entities/animals/rat.xml`
*   `data/entities/animals/iceskull.xml`
*   `data/entities/animals/scavenger_grenade.xml`
*   `data/entities/animals/scavenger_smg.xml`
*   `data/entities/animals/sniper.xml`
*   `data/entities/animals/tank.xml`
*   `data/entities/animals/tank_rocket.xml`

### `g_big_enemies`

This table defines the spawning of larger and more dangerous enemies.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this enemy group spawning.                            |
| `min_count` | The minimum number of entities to spawn.                                 |
| `max_count` | The maximum number of entities to spawn.                                 |
| `entity`    | The XML file path for the entity to spawn.                               |
| `entities`  | A table of entities to spawn, allowing for combinations.                 |

**Key Entities:**

*   `data/entities/animals/thundermage.xml`
*   `data/entities/animals/worm.xml`
*   `data/entities/animals/worm_tiny.xml`
*   `data/entities/animals/iceskull.xml`
*   `data/entities/animals/giant.xml`
*   `data/entities/animals/scavenger_leader.xml`

### `g_scavenger_party`

This table specifically defines the composition of a "scavenger party" encounter.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this encounter spawning.                              |
| `min_count` | The minimum number of entities to spawn.                                 |
| `max_count` | The maximum number of entities to spawn.                                 |
| `entities`  | A table of entities that constitute the scavenger party.                 |

**Key Entities:**

*   `data/entities/animals/scavenger_smg.xml`
*   `data/entities/animals/scavenger_grenade.xml`
*   `data/entities/animals/scavenger_leader.xml`

### `g_unique_enemy` and `g_unique_enemy2`

These tables define the spawning of unique or rarer enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this enemy group spawning.                            |
| `min_count` | The minimum number of entities to spawn.                                 |
| `max_count` | The maximum number of entities to spawn.                                 |
| `entity`    | The XML file path for the entity to spawn.                               |

**Key Entities:**

*   `data/entities/animals/tank.xml`
*   `data/entities/animals/tank_rocket.xml`
*   `data/entities/animals/wizard_tele.xml`
*   `data/entities/animals/wizard_dark.xml`
*   `data/entities/animals/necromancer.xml`

## Item and Prop Spawning

### `g_items`

This table defines the probability of spawning specific items.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this item group spawning.                             |
| `min_count` | The minimum number of items to spawn.                                    |
| `max_count` | The maximum number of items to spawn.                                    |
| `entity`    | The XML file path for the item to spawn.                                 |

**Key Item:**

*   `data/entities/items/wand_level_02.xml`

### `g_lamp`

Controls the spawning of lamps.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this lamp group spawning.                             |
| `min_count` | The minimum number of lamps to spawn.                                    |
| `max_count` | The maximum number of lamps to spawn.                                    |
| `entity`    | The XML file path for the lamp entity.                                   |

**Key Entity:**

*   `data/entities/props/physics_lantern_small.xml`

### `g_props`

Defines the spawning of various physics-enabled props.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this prop group spawning.                             |
| `min_count` | The minimum number of props to spawn.                                    |
| `max_count` | The maximum number of props to spawn.                                    |
| `offset_y`  | Vertical offset for spawning.                                            |
| `entity`    | The XML file path for the prop entity.                                   |

**Key Entities:**

*   `data/entities/props/physics_box_explosive.xml`
*   `data/entities/props/physics_propane_tank.xml`
*   `data/entities/props/physics_barrel_oil.xml`

### `g_skulls`

Controls the spawning of various skull props.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this skull group spawning.                            |
| `min_count` | The minimum number of skulls to spawn.                                   |
| `max_count` | The maximum number of skulls to spawn.                                   |
| `offset_y`  | Vertical offset for spawning.                                            |
| `entity`    | The XML file path for the skull entity.                                  |

**Key Entities:**

*   `data/entities/props/physics_skull_01.xml`
*   `data/entities/props/physics_skull_02.xml`
*   `data/entities/props/physics_skull_03.xml`
*   `data/entities/props/physics_bone_01.xml` (and other bone variants)

### `g_ghostlamp`

Defines the spawning of ghostly lamps.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this lamp group spawning.                             |
| `min_count` | The minimum number of lamps to spawn.                                    |
| `max_count` | The maximum number of lamps to spawn.                                    |
| `offset_y`  | Vertical offset for spawning.                                            |
| `entity`    | The XML file path for the lamp entity.                                   |

**Key Entity:**

*   `data/entities/props/physics_chain_torch_ghostly.xml`

### `g_candles`

Controls the spawning of candles.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | The probability of this candle group spawning.                           |
| `min_count` | The minimum number of candles to spawn.                                  |
| `max_count` | The maximum number of candles to spawn.                                  |
| `entity`    | The XML file path for the candle entity.                                 |

**Key Entities:**

*   `data/entities/props/physics_candle_1.xml`
*   `data/entities/props/physics_candle_2.xml`
*   `data/entities/props/physics_candle_3.xml`

## Pixel Scene Definitions

These tables define various pre-designed "pixel scenes" that can be loaded into the biome, adding unique environmental layouts and structures.

### `g_pixel_scene_01` to `g_pixel_scene_04`

These tables define different sets of pixel scenes with associated probabilities.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `prob`           | The probability of this specific pixel scene being chosen.               |
| `material_file`  | The path to the material PNG file defining the scene's layout.           |
| `visual_file`    | The path to the visual PNG file for the scene's appearance.              |
| `background_file`| The path to the background PNG file for the scene.                       |
| `is_unique`      | Flag indicating if the scene is unique (0 for non-unique).               |

**Examples:**

*   `data/biome_impl/snowcave/verticalobservatory.png`
*   `data/biome_impl/snowcave/icebridge2.png`
*   `data/biome_impl/snowcave/crater.png`
*   `data/biome_impl/snowcave/snowcastle.png`
*   `data/biome_impl/snowcave/icicles.png`

### `g_acidtank_right` and `g_acidtank_left`

These tables define specific acid tank structures.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `prob`           | The probability of this acid tank variant spawning.                      |
| `material_file`  | The path to the material PNG file.                                       |
| `visual_file`    | The path to the visual PNG file.                                         |
| `background_file`| The path to the background PNG file.                                     |
| `is_unique`      | Flag indicating if the scene is unique.                                  |

**Examples:**

*   `data/biome_impl/acidtank_2.png`
*   `data/biome_impl/acidtank.png`

## Helper Functions

These functions are called by the game to trigger specific spawning or loading events.

### `spawn_small_enemies(x, y)`

Spawns small enemies at the given coordinates.

### `spawn_big_enemies(x, y)`

Spawns big enemies at the given coordinates.

### `spawn_unique_enemy(x, y)`

Spawns unique enemies at the given coordinates.

### `spawn_unique_enemy2(x, y)`

Spawns unique enemies (second type) at the given coordinates.

### `spawn_scavenger_party(x, y)`

Spawns a scavenger party at the given coordinates.

### `spawn_items(x, y)`

Spawns items, potentially including a wand altar.

### `spawn_lamp(x, y)`

Spawns a lamp at the given coordinates.

### `spawn_props(x, y)`

Spawns physics props at the given coordinates.

### `spawn_skulls(x, y)`

Spawns skull props at the given coordinates.

### `load_pixel_scene(x, y)`

Loads a random pixel scene from `g_pixel_scene_01`.

### `load_pixel_scene2(x, y)`

Loads a random pixel scene from `g_pixel_scene_02`.

### `load_pixel_scene3(x, y)`

Loads a random pixel scene from `g_pixel_scene_03`.

### `load_pixel_scene4(x, y)`

Loads a random pixel scene from `g_pixel_scene_04`.

### `spawn_altar_torch(x, y)`

Spawns an altar torch at the given coordinates.

### `spawn_acid(x, y)`

Spawns dripping acid gas at the given coordinates.

### `load_altar(x, y)`

Loads an altar structure, including its material, visual, and an associated entity.

### `load_acidtank_right(x, y)`

Loads the right acid tank structure.

### `load_acidtank_left(x, y)`

Loads the left acid tank structure.

### `load_suspension_bridge(x, y)`

Spawns a suspension bridge spawner entity.