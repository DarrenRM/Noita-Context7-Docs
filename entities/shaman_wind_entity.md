---
title: Shaman Wind Entity
category: entities
---

---

# Shaman Wind Entity

This document details the `shaman_wind.xml` entity, representing a "Shaman Wind" creature in Noita. It focuses on its AI behavior, combat capabilities, and physical attributes relevant for modding.

## Core Components

### AnimalAIComponent

This component governs the creature's artificial intelligence and behavior.

| Attribute                  | Value      | Description                                                                 |
| :------------------------- | :--------- | :-------------------------------------------------------------------------- |
| `creature_detection_range_x` | `700`      | Horizontal range within which the creature can detect other creatures.      |
| `creature_detection_range_y` | `10`       | Vertical range within which the creature can detect other creatures.        |
| `food_material`            | `meat`     | The material type considered as food for this creature.                     |
| `needs_food`               | `0`        | Whether the creature requires food to survive (0 = no).                     |
| `sense_creatures`          | `1`        | Whether the creature actively senses other creatures.                         |
| `attack_ranged_enabled`    | `0`        | Whether ranged attacks are enabled (0 = no).                                |
| `attack_melee_enabled`     | `1`        | Whether melee attacks are enabled (1 = yes).                                |
| `aggressiveness_min`       | `95`       | Minimum aggressiveness level.                                               |
| `aggressiveness_max`       | `100`      | Maximum aggressiveness level.                                               |
| `is_static_turret`         | `1`        | Whether the creature acts as a static turret (1 = yes).                     |
| `attack_melee_max_distance`| `15`       | Maximum distance for melee attacks.                                         |
| `attack_melee_damage_min`  | `1.2`      | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`  | `1.6`      | Maximum damage dealt by melee attacks.                                      |

### DamageModelComponent

Defines the creature's health and how it reacts to damage.

| Attribute                   | Value    | Description                                     |
| :-------------------------- | :------- | :---------------------------------------------- |
| `hp`                        | `3`      | Hit points of the creature.                     |
| `ragdoll_material`          | `wood_prop` | Material used for the ragdoll when defeated.    |
| `fire_probability_of_ignition` | `20`     | Percentage chance of igniting from fire damage. |

### SpriteComponent

Specifies the visual representation of the creature.

| Attribute   | Value                         | Description                               |
| :---------- | :---------------------------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/shaman_alt.xml` | Path to the sprite's graphical definition. |

### HitboxComponent

Defines the collision boundaries for the creature.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_max_x`| `6`   | Maximum X-axis extent of the hitbox.      |
| `aabb_max_y`| `0`   | Maximum Y-axis extent of the hitbox.      |
| `aabb_min_x`| `-6`  | Minimum X-axis extent of the hitbox.      |
| `aabb_min_y`| `-12` | Minimum Y-axis extent of the hitbox.      |

### CharacterDataComponent

Provides general character-specific data, including collision and mass.

| Attribute        | Value | Description                                     |
| :--------------- | :---- | :---------------------------------------------- |
| `collision_aabb_min_x` | `-3.0`| Minimum X-axis extent for character collision.  |
| `collision_aabb_max_x` | `3.0` | Maximum X-axis extent for character collision.  |
| `collision_aabb_min_y` | `-6`  | Minimum Y-axis extent for character collision.  |
| `collision_aabb_max_y` | `3`   | Maximum Y-axis extent for character collision.  |
| `mass`           | `2.2` | The mass of the character.                      |

## Other Notable Components

### PathFindingGridMarkerComponent

*   `marker_work_flag`: `16` - Indicates the type of grid marker used for pathfinding.

### GenomeDataComponent

*   `herd_id`: `ghost` - Identifies the creature's herd or group.
*   `food_chain_rank`: `5` - Its position in the food chain.
*   `is_predator`: `1` - Indicates if it's a predator.

### CharacterPlatformingComponent

*   `jump_velocity_y`: `0` - Vertical jump velocity.
*   `run_velocity`: `0` - Running speed.

### PathFindingComponent

*   `can_jump`: `0` - Whether the creature can jump.
*   `can_fly`: `0` - Whether the creature can fly.
*   `can_walk`: `0` - Whether the creature can walk.

### CameraBoundComponent

*   `max_count`: `30` - Maximum number of this entity that can be active within camera bounds.
*   `distance`: `160000` - The radius around the camera within which entities are considered.

### VariableStorageComponent

*   `name`: `mimic_poop_count` - Stores a variable related to mimic behavior.
*   `value_bool`, `value_int`, `value_string`: Initialized to default values.

### LuaComponent

*   `script_source_file`: `data/scripts/animals/mimic_charm.lua` - The Lua script controlling specific behaviors, likely related to mimicry or charming.
*   `execute_every_n_frame`: `183` - The script executes every 183 frames.