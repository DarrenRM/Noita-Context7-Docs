---
title: Wolf Entity
category: entities
---

# Wolf Entity

This document details the attributes of the Wolf entity in Noita, focusing on its AI, combat, and physical characteristics.

## Core Components

The Wolf entity is built upon a `Base` entity, inheriting common functionalities and then extending them with specific components.

### AnimalAIComponent

This component governs the Wolf's behavior, including its combat capabilities, detection, and needs.

| Attribute                       | Value   | Description                                                                 |
| :------------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                      | `1`     | Enables the AI component.                                                   |
| `preferred_job`                 | `JobDefault` | The default job assigned to the wolf.                                       |
| `escape_if_damaged_probability` | `50`    | 50% chance to attempt to escape when damaged.                               |
| `attack_melee_damage_min`       | `0.2`   | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`       | `0.4`   | Maximum damage dealt by melee attacks.                                      |
| `attack_dash_enabled`           | `1`     | Enables the dash attack.                                                    |
| `creature_detection_range_x`    | `300`   | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | `300`   | Vertical range for detecting creatures.                                     |
| `food_material`                 | `meat`  | The material the wolf considers food.                                       |
| `attack_dash_speed`             | `800`   | The speed of the dash attack.                                               |
| `needs_food`                    | `1`     | Indicates that the wolf requires food.                                      |
| `sense_creatures`               | `1`     | Enables the wolf to sense other creatures.                                  |
| `attack_ranged_enabled`         | `0`     | Ranged attacks are disabled for the wolf.                                   |
| `can_fly`                       | `0`     | The wolf cannot fly.                                                        |

### DamageModelComponent

Defines the health and damage-related properties of the Wolf.

| Attribute                 | Value   | Description                                                              |
| :------------------------ | :------ | :----------------------------------------------------------------------- |
| `hp`                      | `0.6`   | The Wolf's health points.                                                |
| `materials_create_messages` | `1`     | When damaged, materials will create messages.                            |
| `ragdoll_material`        | `meat`  | The material used for the wolf's ragdoll.                                |
| `ragdoll_filenames_file`  | `data/ragdolls/wolf/filenames.txt` | Specifies the file containing ragdoll sprite names. |

### SpriteComponent

Handles the visual representation of the Wolf.

| Attribute   | Value                     | Description                               |
| :---------- | :------------------------ | :---------------------------------------- |
| `image_file` | `data/enemies_gfx/wolf.xml` | Path to the sprite definition file.       |
| `offset_x`  | `0`                       | Horizontal offset for the sprite.         |
| `offset_y`  | `0`                       | Vertical offset for the sprite.           |

### PathFindingComponent

Determines how the Wolf navigates the game world.

| Attribute               | Value | Description                                    |
| :---------------------- | :---- | :--------------------------------------------- |
| `distance_to_reach_node_x` | `20`  | Horizontal distance to consider a node reached. |
| `distance_to_reach_node_y` | `20`  | Vertical distance to consider a node reached.   |
| `frames_to_get_stuck`   | `20`  | Frames before the AI considers itself stuck.   |
| `can_jump`              | `0`   | The wolf cannot jump.                          |

### GenomeDataComponent

Provides genetic information relevant to the Wolf's role in the ecosystem.

| Attribute         | Value | Description                               |
| :---------------- | :---- | :---------------------------------------- |
| `herd_id`         | `wolf` | Identifier for the wolf herd.             |
| `food_chain_rank` | `7`   | Its position in the food chain (higher is more dominant). |
| `is_predator`     | `1`   | Indicates that the wolf is a predator.    |

### CharacterPlatformingComponent

Manages the Wolf's movement physics, including acceleration and velocity.

| Attribute                                 | Value | Description                                         |
| :---------------------------------------- | :---- | :-------------------------------------------------- |
| `accel_x`                                 | `4`   | Horizontal acceleration.                            |
| `pixel_gravity`                           | `600` | The strength of gravity affecting the wolf.         |
| `jump_velocity_y`                         | `-12` | The vertical velocity applied when jumping.         |
| `run_velocity`                            | `80`  | The wolf's running speed.                           |
| `run_animation_velocity_switching_enabled` | `1`   | Enables switching animations based on velocity.     |
| `run_animation_velocity_switching_threshold` | `50`  | Velocity threshold for switching run animations.    |

### HitboxComponent

Defines the bounding box used for collision detection.

| Attribute    | Value | Description                               |
| :----------- | :---- | :---------------------------------------- |
| `_enabled`   | `1`   | Enables the hitbox.                       |
| `aabb_min_x` | `-4.5` | Minimum X-coordinate of the bounding box. |
| `aabb_max_x` | `4.5`  | Maximum X-coordinate of the bounding box. |
| `aabb_min_y` | `-5.5` | Minimum Y-coordinate of the bounding box. |
| `aabb_max_y` | `3`    | Maximum Y-coordinate of the bounding box. |

### CharacterDataComponent

Contains general character data, including collision and mass.

| Attribute              | Value | Description                                       |
| :--------------------- | :---- | :------------------------------------------------ |
| `_enabled`             | `1`   | Enables the character data component.             |
| `climb_over_y`         | `4`   | Vertical distance the character can climb over.   |
| `collision_aabb_min_x` | `-2.0` | Minimum X-coordinate for collision.               |
| `collision_aabb_max_x` | `2.0`  | Maximum X-coordinate for collision.               |
| `collision_aabb_min_y` | `-3`   | Minimum Y-coordinate for collision.               |
| `collision_aabb_max_y` | `3`    | Maximum Y-coordinate for collision.               |
| `buoyancy_check_offset_y` | `-6` | Vertical offset for buoyancy checks.              |
| `mass`                 | `1.2` | The mass of the character.                        |

### CameraBoundComponent

Manages how the camera interacts with the entity.

| Attribute   | Value     | Description                                     |
| :---------- | :-------- | :---------------------------------------------- |
| `max_count` | `20`      | Maximum number of this entity the camera tracks. |
| `distance`  | `160000`  | The distance at which the entity is tracked.    |