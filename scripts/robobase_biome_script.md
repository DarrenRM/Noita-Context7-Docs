---
title: Robobase Biome Script
category: scripts/
---

# Robobase Biome Script

This script defines the entities and behaviors for the "Robobase" biome in Noita. It handles the spawning of various enemies, props, and special structures within this biome.

## Core Dependencies

The script relies on several other core Noita Lua files for its functionality:

*   `data/scripts/director_helpers.lua`: Provides general helper functions for entity spawning and management.
*   `data/scripts/director_helpers_design.lua`: Contains design-specific helper functions.
*   `data/scripts/biome_scripts.lua`: Base script for biome definitions.
*   `data/scripts/lib/utilities.lua`: Utility functions.
*   `data/scripts/biome_modifiers.lua`: Functions for applying biome modifiers.
*   `data/scripts/items/generate_shop_item.lua`: Handles the generation of shop items.

## Registered Spawn Functions

These functions are registered to be called by the game's director system at specific points or based on certain conditions.

*   `load_warning_strip`: Loads a warning strip background sprite.
*   `spawn_turret`: Spawns turrets.
*   `spawn_vines`: Spawns vines.
*   `spawn_hanging_prop`: Spawns hanging props.
*   `spawn_barricade`: Spawns barricades.
*   `spawn_shopitem`: Spawns shop items.
*   `spawn_lasergate_ver`: Spawns vertical laser gates.

## Enemy Spawning Tables

These tables define the probabilities and types of enemies that can spawn within the Robobase biome.

### `g_small_enemies`

Defines the pool of smaller enemies that can appear.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `0.8`                                              |
| `min_count` | Minimum number of entities to spawn.            | `0`                                                |
| `max_count` | Maximum number of entities to spawn.            | `0`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/animals/roboguard_big.xml`          |
|             |                                                 | `data/entities/animals/basebot_sentry.xml`         |
|             |                                                 | `data/entities/animals/basebot_hidden.xml`         |
|             |                                                 | `data/entities/animals/basebot_neutralizer.xml`    |
|             |                                                 | `data/entities/animals/basebot_soldier.xml`        |
|             |                                                 | `data/entities/animals/vault/scavenger_glue.xml`   |
|             |                                                 | `data/entities/animals/robobase/healerdrone_physics.xml` |

### `g_big_enemies`

Defines the pool of larger, more formidable enemies.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `0.8`                                              |
| `min_count` | Minimum number of entities to spawn.            | `0`                                                |
| `max_count` | Maximum number of entities to spawn.            | `0`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/animals/robobase/drone_shield.xml`    |
|             |                                                 | `data/entities/animals/basebot_hidden.xml`         |
|             |                                                 | `data/entities/animals/basebot_neutralizer.xml`    |
|             |                                                 | `data/entities/animals/basebot_sentry.xml`         |
|             |                                                 | `data/entities/animals/basebot_soldier.xml`        |
|             |                                                 | `data/entities/animals/robobase/tank_super.xml`    |
|             |                                                 | `data/entities/animals/necrobot.xml`               |
|             |                                                 | `data/entities/animals/necrobot_super.xml`         |

## Prop and Decoration Spawning Tables

These tables control the spawning of various environmental props and decorative elements.

### `g_lamp`

Defines the types of lamps that can spawn.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `0.4`                                              |
| `min_count` | Minimum number of entities to spawn.            | `1`                                                |
| `max_count` | Maximum number of entities to spawn.            | `1`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/props/physics_tubelamp.xml`         |
| `offset_y`  | Vertical offset for spawning.                   | `-4`                                               |
|             |                                                 | `data/entities/props/dripping_water.xml`           |
|             |                                                 | `data/entities/props/dripping_water_heavy.xml`     |
|             |                                                 | `data/entities/props/dripping_oil.xml`             |
|             |                                                 | `data/entities/props/dripping_radioactive.xml`     |

### `g_props`

Defines the types of physics-enabled props, such as barrels and tanks.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `0.4`                                              |
| `min_count` | Minimum number of entities to spawn.            | `0`                                                |
| `max_count` | Maximum number of entities to spawn.            | `0`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/props/physics_box_explosive.xml`    |
| `offset_y`  | Vertical offset for spawning.                   | `-8`                                               |
|             |                                                 | `data/entities/props/physics_barrel_radioactive.xml` |
|             |                                                 | `data/entities/props/physics_barrel_oil.xml`       |
|             |                                                 | `data/entities/props/physics_pressure_tank.xml`    |
|             |                                                 | `data/entities/props/physics_propane_tank.xml`     |
|             |                                                 | `data/entities/props/physics_seamine.xml`          |

### `g_hanging_props`

Defines props that hang from the ceiling or other structures.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `1.0`                                              |
| `min_count` | Minimum number of entities to spawn.            | `1`                                                |
| `max_count` | Maximum number of entities to spawn.            | `1`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/props/suspended_container.xml`      |
|             |                                                 | `data/entities/props/suspended_tank_radioactive.xml` |
|             |                                                 | `data/entities/props/suspended_tank_acid.xml`      |
|             |                                                 | `data/entities/props/suspended_seamine.xml`        |

### `g_ghostlamp`

Defines ghostly lamps.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `1.0`                                              |
| `min_count` | Minimum number of entities to spawn.            | `1`                                                |
| `max_count` | Maximum number of entities to spawn.            | `1`                                                |
| `offset_y`  | Vertical offset for spawning.                   | `10`                                               |
| `entity`    | Path to the entity's XML definition.            | `data/entities/props/physics_chain_torch_ghostly.xml` |

### `g_turret`

Defines the types of turrets that can spawn.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `0.5`                                              |
| `min_count` | Minimum number of entities to spawn.            | `0`                                                |
| `max_count` | Maximum number of entities to spawn.            | `0`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/animals/vault/turret_right.xml`     |
|             |                                                 | `data/entities/animals/vault/turret_left.xml`      |

### `g_candles`

Defines the types of candles that can spawn.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `0.33`                                             |
| `min_count` | Minimum number of entities to spawn.            | `1`                                                |
| `max_count` | Maximum number of entities to spawn.            | `1`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/props/physics_candle_1.xml`         |
|             |                                                 | `data/entities/props/physics_candle_2.xml`         |
|             |                                                 | `data/entities/props/physics_candle_3.xml`         |

### `g_vines`

Defines the types of vines that can spawn.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `0.5`                                              |
| `min_count` | Minimum number of entities to spawn.            | `1`                                                |
| `max_count` | Maximum number of entities to spawn.            | `1`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/props/physics_hanging_wire.xml`     |

### `g_barricade`

Defines the types of barricades that can spawn.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this entity spawning.            | `1.0`                                              |
| `min_count` | Minimum number of entities to spawn.            | `1`                                                |
| `max_count` | Maximum number of entities to spawn.            | `1`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/props/physics_box_harmless.xml`     |

## Item Spawning Table

### `g_items`

Defines the pool of items that can spawn, primarily wands.

| Attribute   | Description                                     | Example Entity                                     |
| :---------- | :---------------------------------------------- | :------------------------------------------------- |
| `prob`      | Probability of this item spawning.              | `5`                                                |
| `min_count` | Minimum number of items to spawn.               | `1`                                                |
| `max_count` | Maximum number of items to spawn.               | `1`                                                |
| `entity`    | Path to the entity's XML definition.            | `data/entities/items/wand_level_05.xml`            |
|             |                                                 | `data/entities/items/wand_level_05_better.xml`     |
|             |                                                 | `data/entities/items/wand_unshuffle_03.xml`        |
|             |                                                 | `data/entities/items/wand_unshuffle_04.xml`        |

## Spawn Functions

These functions are the actual implementations called by the game to spawn entities based on the tables defined above.

### `spawn_small_enemies(x, y)`

Spawns small enemies at the given coordinates.

### `spawn_big_enemies(x, y)`

Spawns big enemies at the given coordinates.

### `spawn_items(x, y)`

Spawns items, with a chance to load a special "wand altar vault" pixel scene.

### `spawn_lamp(x, y)`

Spawns lamps at the given coordinates.

### `spawn_props(x, y)`

Spawns general props at the given coordinates.

### `spawn_hanging_prop(x, y)`

Spawns hanging props at the given coordinates.

### `spawn_turret(x, y)`

Spawns turrets at the given coordinates.

### `load_pixel_scene(x, y)`

Loads a random pixel scene from `g_pixel_scene_01`.

### `load_pixel_scene2(x, y)`

Loads a random pixel scene from `g_pixel_scene_02`.

### `load_warning_strip(x, y)`

Loads a warning strip background sprite.

### `spawn_vines(x, y)`

Spawns vines with an offset.

### `spawn_potion_altar(x, y)`

Spawns a potion altar pixel scene with a probability check.

### `spawn_barricade(x, y)`

Spawns barricades at the given coordinates.

### `spawn_shopitem(x, y)`

Generates a shop item at the given coordinates.

### `spawn_lasergate_ver(x, y)`

Loads a vertical laser gate entity.