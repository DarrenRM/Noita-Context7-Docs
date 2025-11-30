---
title: Dark Alchemist Entity
category: entities
---

# Dark Alchemist Entity

This document details the configuration of the Dark Alchemist entity in Noita, focusing on its AI, combat, and physical attributes.

## Core Attributes

The Dark Alchemist is a hostile entity with aggressive AI, designed to engage in melee combat. It is a static turret-like enemy, meaning it does not move from its position.

### `Base` Entity Configuration

The entity inherits core functionality from `base_enemy_basic.xml`.

### `AnimalAIComponent`

This component governs the creature's behavior and senses.

| Attribute                     | Value   | Description                                                                 |
| :---------------------------- | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                    | `1`     | Enables the AI component.                                                   |
| `preferred_job`               | `JobDefault` | Default job assignment for the AI.                                          |
| `escape_if_damaged_probability` | `0`     | The creature will not attempt to flee when damaged.                         |
| `creature_detection_range_x`  | `700`   | Horizontal range for detecting other creatures.                             |
| `creature_detection_range_y`  | `10`    | Vertical range for detecting other creatures.                               |
| `food_material`               | `meat`  | The material it consumes for sustenance (though `needs_food` is `0`).       |
| `needs_food`                  | `0`     | The creature does not require food to survive.                              |
| `sense_creatures`             | `1`     | Enables the creature to sense other creatures.                              |
| `attack_ranged_enabled`       | `0`     | Ranged attacks are disabled.                                                |
| `attack_melee_enabled`        | `1`     | Melee attacks are enabled.                                                  |
| `can_fly`                     | `0`     | The creature cannot fly.                                                    |
| `attack_melee_action_frame`   | `5`     | The animation frame at which the melee attack is executed.                  |
| `aggressiveness_min`          | `95`    | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | `100`   | Maximum aggressiveness level.                                               |
| `is_static_turret`            | `1`     | The entity remains stationary.                                              |
| `attack_melee_max_distance`   | `15`    | Maximum distance for performing a melee attack.                             |
| `attack_melee_damage_min`     | `1.2`   | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`     | `1.6`   | Maximum damage dealt by melee attacks.                                      |

### `DamageModelComponent`

Defines the entity's health and damage-related properties.

| Attribute                     | Value   | Description                                                                 |
| :---------------------------- | :------ | :-------------------------------------------------------------------------- |
| `hp`                          | `3`     | Hit points of the Dark Alchemist.                                           |
| `ragdoll_material`            | `wood_prop` | The material used for its ragdoll when defeated.                            |
| `ragdoll_filenames_file`      | `""`    | No specific ragdoll file is defined, likely uses default.                   |
| `blood_material`              | `""`    | No specific blood material is defined.                                      |
| `fire_probability_of_ignition`| `20`    | 20% chance of igniting when exposed to fire.                                |

### `SpriteComponent`

Determines the visual representation of the entity.

| Attribute   | Value                         | Description                                     |
| :---------- | :---------------------------- | :---------------------------------------------- |
| `image_file`| `data/enemies_gfx/coward_alt.xml` | Path to the sprite definition file.             |
| `offset_x`  | `0`                           | Horizontal offset for the sprite.               |
| `offset_y`  | `0`                           | Vertical offset for the sprite.                 |

### `PathFindingGridMarkerComponent`

Used for pathfinding calculations.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `marker_work_flag`| `16`  | A flag indicating the type of work or area this entity occupies for pathfinding. |

### `GenomeDataComponent`

Provides genetic information, influencing its role in the ecosystem.

| Attribute         | Value   | Description                                                                 |
| :---------------- | :------ | :-------------------------------------------------------------------------- |
| `herd_id`         | `ghost` | Identifies the herd or group this creature belongs to.                      |
| `food_chain_rank` | `5`     | Its position in the food chain (higher numbers are typically higher ranks). |
| `is_predator`     | `1`     | Indicates that this creature is a predator.                                 |

### `CharacterPlatformingComponent`

Defines movement capabilities related to platforming.

| Attribute         | Value | Description                                                                 |
| :---------------- | :---- | :-------------------------------------------------------------------------- |
| `jump_velocity_y` | `0`   | The creature has no vertical jump velocity.                                 |
| `run_velocity`    | `0`   | The creature has no horizontal running velocity.                            |

### `PathFindingComponent`

Configures how the entity navigates the environment.

| Attribute | Value | Description                                                                 |
| :-------- | :---- | :-------------------------------------------------------------------------- |
| `can_jump`| `0`   | The creature cannot jump.                                                   |
| `can_fly` | `0`   | The creature cannot fly.                                                    |
| `can_walk`| `0`   | The creature cannot walk (consistent with `is_static_turret`).              |

### `CameraBoundComponent`

Controls how the entity interacts with the camera's view.

| Attribute   | Value   | Description                                                                 |
| :---------- | :------ | :-------------------------------------------------------------------------- |
| `max_count` | `30`    | Maximum number of this entity that can be active within camera bounds.      |
| `distance`  | `160000`| The distance threshold for the camera to consider this entity.              |

### `HitboxComponent`

Defines the collision boundaries for the entity.

| Attribute   | Value | Description                                                                 |
| :---------- | :---- | :-------------------------------------------------------------------------- |
| `_enabled`  | `1`   | Enables the hitbox.                                                         |
| `aabb_max_x`| `6`   | Maximum X-axis extent of the Axis-Aligned Bounding Box.                     |
| `aabb_max_y`| `0`   | Maximum Y-axis extent of the Axis-Aligned Bounding Box.                     |
| `aabb_min_x`| `-6`  | Minimum X-axis extent of the Axis-Aligned Bounding Box.                     |
| `aabb_min_y`| `-12` | Minimum Y-axis extent of the Axis-Aligned Bounding Box.                     |

### `CharacterDataComponent`

General character data, including collision and mass.

| Attribute          | Value | Description                                                                 |
| :----------------- | :---- | :-------------------------------------------------------------------------- |
| `collision_aabb_min_x` | `-3.0`| Minimum X-axis extent for character collision.                              |
| `collision_aabb_max_x` | `3.0` | Maximum X-axis extent for character collision.                              |
| `collision_aabb_min_y` | `-6`  | Minimum Y-axis extent for character collision.                              |
| `collision_aabb_max_y` | `3`   | Maximum Y-axis extent for character collision.                              |
| `mass`             | `2.2` | The mass of the character.                                                  |

## Additional Components

### `VariableStorageComponent`

Used for storing entity-specific variables.

| Attribute     | Value | Description                                                                 |
| :------------ | :---- | :-------------------------------------------------------------------------- |
| `_enabled`    | `1`   | Enables the variable storage.                                               |
| `name`        | `mimic_poop_count` | The name of the variable.                                                   |
| `value_bool`  | `0`   | Boolean value (false).                                                      |
| `value_int`   | `0`   | Integer value (0).                                                          |
| `value_string`| `""`  | String value (empty).                                                       |

### `LuaComponent`

Attaches a Lua script to the entity for custom behavior.

| Attribute           | Value                                | Description                                                                 |
| :------------------ | :----------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`          | `1`                                  | Enables the Lua component.                                                  |
| `script_source_file`| `data/scripts/animals/mimic_charm.lua` | The path to the Lua script file.                                            |
| `execute_every_n_frame`| `183`                                | The script will execute every 183 frames.                                   |