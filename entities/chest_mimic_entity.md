---
title: Chest Mimic Entity
category: entities
---

# Chest Mimic Entity

This document details the configuration of the Chest Mimic entity in Noita, focusing on its AI, combat, and physical properties.

## Base Entity Configuration

The Chest Mimic inherits its core functionality from `base_enemy_basic.xml`.

## Key Components

### AnimalAIComponent

This component governs the creature's behavior and AI.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `creature_detection_range_x`  | `700`                               | Horizontal range at which the mimic detects creatures.                      |
| `creature_detection_range_y`  | `10`                                | Vertical range at which the mimic detects creatures.                        |
| `food_material`               | `meat`                              | The type of material the creature consumes (though it doesn't need food).   |
| `needs_food`                  | `0`                                 | Indicates that the mimic does not require food to survive.                  |
| `sense_creatures`             | `1`                                 | Enables the mimic to sense nearby creatures.                                |
| `attack_ranged_enabled`       | `0`                                 | Ranged attacks are disabled for this entity.                                |
| `attack_melee_enabled`        | `1`                                 | Melee attacks are enabled.                                                  |
| `can_fly`                     | `0`                                 | The mimic cannot fly.                                                       |
| `attack_melee_action_frame`   | `5`                                 | The frame within its animation cycle when the melee attack is performed.    |
| `aggressiveness_min`          | `95`                                | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | `100`                               | Maximum aggressiveness level.                                               |
| `is_static_turret`            | `1`                                 | The mimic acts as a static turret, not moving to pursue targets.            |
| `attack_melee_max_distance`   | `15`                                | Maximum distance for a melee attack.                                        |
| `attack_melee_damage_min`     | `0.6`                               | Minimum damage dealt by a melee attack.                                     |
| `attack_melee_damage_max`     | `1.0`                               | Maximum damage dealt by a melee attack.                                     |

### DamageModelComponent

Defines the health and damage-related properties of the mimic.

| Attribute                     | Value      | Description                                                              |
| :---------------------------- | :--------- | :----------------------------------------------------------------------- |
| `hp`                          | `3`        | The total hit points of the Chest Mimic.                                 |
| `ragdoll_material`            | `wood_prop`| The material used for the ragdoll effect when defeated.                  |
| `fire_probability_of_ignition`| `20`       | The percentage chance of igniting from fire damage.                      |

### SpriteComponent

Specifies the visual representation of the mimic.

| Attribute   | Value                           | Description                               |
| :---------- | :------------------------------ | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/chest_mimic.xml`| Path to the sprite definition file.       |

### HitboxComponent

Defines the collision boundaries for interactions.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_max_x`| `8`   | Maximum X-axis extent of the hitbox.      |
| `aabb_max_y`| `3`   | Maximum Y-axis extent of the hitbox.      |
| `aabb_min_x`| `-8`  | Minimum X-axis extent of the hitbox.      |
| `aabb_min_y`| `-12` | Minimum Y-axis extent of the hitbox.      |

### CharacterDataComponent

Provides general character physics and collision data.

| Attribute          | Value | Description                                     |
| :----------------- | :---- | :---------------------------------------------- |
| `collision_aabb_min_x` | `-6.0`| Minimum X-axis extent for character collision.  |
| `collision_aabb_max_x` | `6.0` | Maximum X-axis extent for character collision.  |
| `collision_aabb_min_y` | `-10` | Minimum Y-axis extent for character collision.  |
| `collision_aabb_max_y` | `3`   | Maximum Y-axis extent for character collision.  |
| `mass`             | `2.2` | The mass of the character.                      |

### LuaComponent

Attaches custom Lua scripting to the entity.

| Attribute         | Value                                | Description                                                              |
| :---------------- | :----------------------------------- | :----------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/animals/mimic_charm.lua`| The Lua script file responsible for specific mimic behaviors.            |
| `execute_every_n_frame`| `183`                                | How often the script is executed (in frames).                            |

### VariableStorageComponent

Allows for storing custom variables associated with the entity.

| Attribute | Value | Description                                                              |
| :-------- | :---- | :----------------------------------------------------------------------- |
| `name`    | `mimic_poop_count` | The name of the variable.                                                |
| `value_int`| `0`   | Initial integer value for `mimic_poop_count`.                            |