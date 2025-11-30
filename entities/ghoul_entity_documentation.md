---
title: Ghoul Entity Documentation
category: entities
---

# Ghoul Entity Documentation

This document details the key attributes of the Ghoul entity in Noita, useful for AI-assisted modding.

## Core Attributes

The Ghoul is a basic enemy with ranged attack capabilities.

### AnimalAIComponent

This component governs the Ghoul's behavior and combat actions.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault`                        | Default job assigned to the entity.                                         |
| `escape_if_damaged_probability` | `70`                                | 70% chance to attempt escape when damaged.                                  |
| `attack_melee_damage_min`     | `0.6`                               | Minimum melee damage. (Note: Melee is disabled for this entity).            |
| `attack_melee_damage_max`     | `1.0`                               | Maximum melee damage. (Note: Melee is disabled for this entity).            |
| `attack_ranged_max_distance`  | `40`                                | Maximum distance for ranged attacks.                                        |
| `creature_detection_range_x`  | `300`                               | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `300`                               | Vertical range for detecting creatures.                                     |
| `food_material`               | `blood`                             | Material the Ghoul prefers to consume (though `needs_food` is 0).           |
| `sense_creatures`             | `1`                                 | Enables creature sensing.                                                   |
| `attack_ranged_enabled`       | `1`                                 | Enables ranged attacks.                                                     |
| `attack_melee_enabled`        | `0`                                 | Disables melee attacks.                                                     |
| `attack_ranged_entity_file`   | `data/entities/projectiles/acidshot_slow.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_frames_between`| `5`                                 | Number of frames between ranged attacks.                                    |

### DamageModelComponent

Defines the Ghoul's health and how it reacts to damage.

| Attribute                 | Value                                     | Description                                                              |
| :------------------------ | :---------------------------------------- | :----------------------------------------------------------------------- |
| `hp`                      | `3`                                       | Hit points of the Ghoul.                                                 |
| `ragdoll_material`        | `meat`                                    | Material used for the ragdoll when defeated.                             |
| `blood_material`          | `slime`                                   | Material of the blood sprayed.                                           |
| `blood_spray_material`    | `slime`                                   | Material of the blood spray particles.                                   |
| `fire_probability_of_ignition` | `5`                                   | 5% chance to ignite from fire damage.                                    |
| `blood_sprite_directional`| `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` | Sprite for directional blood splatters.                                |
| `blood_sprite_large`      | `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` | Sprite for large blood splatters.                                        |

### SpriteComponent

Specifies the visual representation of the Ghoul.

| Attribute   | Value                         | Description                               |
| :---------- | :---------------------------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/ghoul.xml`  | Path to the Ghoul's sprite definition.    |

### PathFindingComponent

Controls the Ghoul's movement and pathfinding capabilities.

| Attribute                   | Value | Description                                     |
| :-------------------------- | :---- | :---------------------------------------------- |
| `distance_to_reach_node_x`  | `20`  | Horizontal distance to consider a node reached. |
| `distance_to_reach_node_y`  | `20`  | Vertical distance to consider a node reached.   |
| `frames_to_get_stuck`       | `120` | Frames before entity is considered stuck.       |
| `can_jump`                  | `1`   | Allows the Ghoul to jump.                       |
| `jump_speed`                | `100` | Speed of the jump.                              |
| `initial_jump_max_distance_x`| `80`  | Maximum horizontal distance of a jump.          |
| `initial_jump_max_distance_y`| `60`  | Maximum vertical distance of a jump.            |

### CharacterPlatformingComponent

Defines basic character movement parameters.

| Attribute     | Value | Description                               |
| :------------ | :---- | :---------------------------------------- |
| `jump_velocity_y` | `-12` | Vertical velocity applied when jumping.   |
| `run_velocity`    | `12`  | Horizontal movement speed.                |

### HitboxComponent

Defines the collision area of the Ghoul.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_max_x`| `4`   | Maximum X-axis extent of the hitbox.      |
| `aabb_max_y`| `4`   | Maximum Y-axis extent of the hitbox.      |
| `aabb_min_x`| `-4`  | Minimum X-axis extent of the hitbox.      |
| `aabb_min_y`| `-12` | Minimum Y-axis extent of the hitbox.      |