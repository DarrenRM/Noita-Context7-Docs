---
title: Statue Entity Configuration
category: entities
---

# Statue Entity Configuration

This document details the configuration of the "Statue" entity in Noita, focusing on its AI, combat, and physical properties for modding purposes.

## Core Components

The Statue entity is built upon a `Base` entity, inheriting its fundamental behaviors and properties.

### `Base` Entity Inheritance

The Statue inherits from `data/entities/base_enemy_flying.xml`, indicating it shares characteristics with other flying enemies.

## Key Components and Attributes

### `AnimalAIComponent`

This component governs the Statue's artificial intelligence and behavior.

| Attribute                     | Description                                                                 | Value Examples        |
| :---------------------------- | :-------------------------------------------------------------------------- | :-------------------- |
| `_enabled`                    | Enables or disables the AI component.                                       | `1` (enabled)         |
| `preferred_job`               | The primary task the AI will attempt to perform.                            | `JobDefault`          |
| `escape_if_damaged_probability` | Probability of attempting to flee when damaged.                             | `100` (always flees)  |
| `attack_melee_damage_min`     | Minimum damage dealt by melee attacks.                                      | `0.4`                 |
| `attack_melee_damage_max`     | Maximum damage dealt by melee attacks.                                      | `0.7`                 |
| `creature_detection_range_x`  | Horizontal range for detecting creatures.                                   | `400`                 |
| `creature_detection_range_y`  | Vertical range for detecting creatures.                                     | `400`                 |
| `creature_detection_angular_range_deg` | Angular range (in degrees) for creature detection.                      | `60`                  |
| `attack_melee_max_distance`   | Maximum distance for initiating a melee attack.                             | `20`                  |
| `food_material`               | The material considered "food" for this creature.                           | `meat`                |
| `needs_food`                  | Whether the creature requires food to survive.                              | `0` (does not need)   |
| `sense_creatures`             | Whether the AI actively senses nearby creatures.                            | `1` (senses)          |
| `can_fly`                     | Allows the entity to fly.                                                   | `1` (can fly)         |
| `attack_melee_enabled`        | Enables melee attacks.                                                      | `1` (enabled)         |
| `aggressiveness_min`          | Minimum aggressiveness level.                                               | `90`                  |
| `aggressiveness_max`          | Maximum aggressiveness level.                                               | `100`                 |

### `DamageModelComponent`

Defines the health, damage resistances, and how the entity reacts to damage.

| Attribute                   | Description                                                                 | Value Examples        |
| :-------------------------- | :-------------------------------------------------------------------------- | :-------------------- |
| `hp`                        | Hit points of the entity.                                                   | `7`                   |
| `materials_create_messages` | Whether damage events create messages.                                      | `1`                   |
| `ragdoll_fx_forced`         | The visual effect applied when the entity is ragdolled.                     | `DISINTEGRATED`       |
| `ragdoll_material`          | The material used for the ragdoll.                                          | `rock_static_glow`    |
| `minimum_knockback_force`   | Minimum force required to knock the entity back.                            | `1000`                |
| `air_needed`                | Whether the entity requires air.                                            | `0` (does not need)   |

#### `damage_multipliers`

Specifies multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `1.0`      |
| `projectile`| `0.0`      |
| `explosion` | `0.0`      |
| `electricity`| `0.0`      |
| `slice`     | `0.0`      |
| `ice`       | `0.0`      |
| `fire`      | `0.0`      |

### `SpriteComponent`

Determines the visual appearance of the entity.

| Attribute    | Description                               | Value Examples              |
| :----------- | :---------------------------------------- | :-------------------------- |
| `image_file` | Path to the sprite image definition file. | `data/enemies_gfx/statue.xml` |
| `offset_x`   | Horizontal offset for the sprite.         | `0`                         |
| `offset_y`   | Vertical offset for the sprite.           | `0`                         |

### `PathFindingComponent`

Configures how the entity navigates the game world.

| Attribute                   | Description                                     | Value Examples |
| :-------------------------- | :---------------------------------------------- | :------------- |
| `can_jump`                  | Whether the entity can jump.                    | `1`            |
| `can_fly`                   | Whether the entity can fly.                     | `1`            |
| `can_walk`                  | Whether the entity can walk.                    | `1`            |
| `jump_speed`                | The speed at which the entity jumps.            | `80`           |
| `initial_jump_lob`          | The initial upward force of a jump.             | `1`            |
| `initial_jump_max_distance_x` | Maximum horizontal distance of a jump.          | `60`           |
| `initial_jump_max_distance_y` | Maximum vertical distance of a jump.            | `60`           |

### `CharacterPlatformingComponent`

Defines movement parameters for characters, including flying speed.

| Attribute        | Description                               | Value Examples |
| :--------------- | :---------------------------------------- | :------------- |
| `fly_speed_change_spd` | Speed modifier for flying.                | `0.8`          |
| `fly_velocity_x` | Horizontal velocity when flying.          | `28`           |
| `accel_x`        | Horizontal acceleration.                  | `0.03`         |
| `jump_velocity_y`| Vertical velocity when jumping.           | `-12`          |
| `run_velocity`   | Horizontal velocity when running.         | `17`           |

### `HitboxComponent`

Defines the collision boundaries of the entity.

| Attribute   | Description                               | Value Examples |
| :---------- | :---------------------------------------- | :------------- |
| `aabb_max_x`| Maximum X-coordinate of the bounding box. | `3`            |
| `aabb_max_y`| Maximum Y-coordinate of the bounding box. | `3`            |
| `aabb_min_x`| Minimum X-coordinate of the bounding box. | `-3`           |
| `aabb_min_y`| Minimum Y-coordinate of the bounding box. | `-14`          |

## Additional Components

### `LightComponent`

Adds a light source to the entity.

| Attribute     | Description                               | Value Examples |
| :------------ | :---------------------------------------- | :------------- |
| `_enabled`    | Enables or disables the light component.  | `1`            |
| `radius`      | The radius of the light.                  | `50`           |
| `fade_out_time`| Time it takes for the light to fade out.  | `1.5`          |

### `ItemPickUpperComponent`

Allows the entity to pick up items.

| Attribute   | Description                               | Value Examples |
| :---------- | :---------------------------------------- | :------------- |
| `is_in_npc` | Indicates if the entity is an NPC.        | `1`            |

### `GameEffectComponent` (Multiple Instances)

These components grant the Statue passive protection effects.

| Effect Type        | Description                               | Frames |
| :----------------- | :---------------------------------------- | :----- |
| `PROTECTION_PROJECTILE` | Grants protection against projectiles.    | `-1`   |
| `PROTECTION_EXPLOSION`  | Grants protection against explosions.     | `-1`   |
| `PROTECTION_ELECTRICITY`| Grants protection against electricity.    | `-1`   |

*Note: `frames="-1"` indicates the effect is permanent.*