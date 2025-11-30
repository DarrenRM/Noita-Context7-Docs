---
title: Base Hidden Bot Entity
category: entities
---

# Base Hidden Bot Entity

This document describes the `basebot_hidden.xml` entity, a flying, invisible robotic enemy in Noita.

## Core Components

The `basebot_hidden.xml` entity inherits from `base_enemy_robot.xml` and includes several key components that define its behavior and appearance.

### AnimalAIComponent

This component governs the AI and combat behavior of the hidden bot.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `creature_detection_range_x` | Horizontal range for detecting creatures.                                |
| `creature_detection_range_y` | Vertical range for detecting creatures.                                  |
| `sense_creatures`         | Enables creature sensing.                                                |
| `attack_ranged_enabled`   | Enables ranged attacks.                                                  |
| `attack_ranged_entity_file` | Path to the projectile entity used for ranged attacks (`hiddenshot.xml`). |
| `attack_ranged_max_distance` | Maximum distance for ranged attacks.                                     |
| `attack_ranged_frames_between` | Delay in frames between ranged attacks.                                  |
| `can_fly`                 | Allows the entity to fly.                                                |
| `can_walk`                | Disables walking.                                                        |

### DamageModelComponent

Defines the health and damage resistances of the entity.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `hp`                   | Health points of the entity.                                             |
| `ragdoll_filenames_file` | Specifies the ragdoll files for the entity.                              |
| `damage_multipliers`   | Modifiers for incoming damage types.                                     |
| `projectile`           | Damage multiplier for projectiles (0.0 means immune).                    |
| `electricity`          | Damage multiplier for electricity (-1.0 means immune/healed).            |

### SpriteComponent

Controls the visual representation of the entity.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `image_file`  | Path to the sprite's image definition.    |

### PathFindingComponent

Determines how the entity navigates the environment.

| Attribute | Description |
| :-------- | :---------- |
| `can_fly` | Allows flight. |
| `can_walk`| Disables walking. |

### CharacterPlatformingComponent

Manages movement capabilities, especially flight.

| Attribute           | Description                               |
| :------------------ | :---------------------------------------- |
| `fly_speed_max_up`  | Maximum upward flight speed.              |
| `fly_speed_max_down`| Maximum downward flight speed.            |
| `fly_speed_mult`    | Multiplier for flight speed.              |
| `fly_velocity_x`    | Horizontal flight speed.                  |

### HitboxComponent

Defines the collision area for the entity.

| Attribute    | Description                               |
| :----------- | :---------------------------------------- |
| `aabb_min_x` | Minimum X-axis coordinate of the bounding box. |
| `aabb_max_x` | Maximum X-axis coordinate of the bounding box. |
| `aabb_min_y` | Minimum Y-axis coordinate of the bounding box. |
| `aabb_max_y` | Maximum Y-axis coordinate of the bounding box. |

### CharacterDataComponent

Provides general character properties.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `mass`    | The mass of the character.                |

## Special Effects

The hidden bot possesses several inherent game effects applied via separate `Entity` blocks.

### Invisibility and Protections

The entity is granted permanent invisibility and immunity to freeze and projectiles.

| Effect            | Description                               |
| :---------------- | :---------------------------------------- |
| `INVISIBILITY`    | Makes the entity invisible.               |
| `PROTECTION_FREEZE`| Grants immunity to freezing.              |
| `PROTECTION_PROJECTILE`| Grants immunity to projectiles.       |

These effects are applied with `frames="-1"`, indicating they are permanent for the entity's lifetime.