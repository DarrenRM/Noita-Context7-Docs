---
title: Base Enemy - Basic Humanoid
category: entities
---

# Base Enemy - Basic Humanoid

This document details the core components of a basic humanoid enemy entity in Noita, serving as a foundational template for more specialized enemies.

## Key Components and Attributes

### Base Entity Inheritance

This entity inherits from `data/entities/base_humanoid.xml`, meaning it shares fundamental properties with other humanoid entities.

### AnimalAIComponent

Controls the AI behavior of the creature.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `preferred_job`           | Sets the AI's default behavior (e.g., `JobDefault`).                     |
| `creature_detection_range_x` | Horizontal range (in pixels) for detecting other creatures.              |
| `creature_detection_range_y` | Vertical range (in pixels) for detecting other creatures.                |
| `attack_melee_damage_min` | Minimum damage dealt by melee attacks.                                   |
| `attack_melee_damage_max` | Maximum damage dealt by melee attacks.                                   |
| `food_material`           | The material this creature considers food (e.g., `meat`).                |
| `needs_food`              | Whether the creature requires food to survive (`1` for yes, `0` for no). |
| `sense_creatures`         | Whether the creature can sense other creatures (`1` for yes, `0` for no). |
| `aggressiveness_min`      | Minimum aggressiveness level.                                            |
| `aggressiveness_max`      | Maximum aggressiveness level.                                            |

### DamageModelComponent

Defines the health and damage-related properties of the entity.

| Attribute              | Description                                                                                             |
| :--------------------- | :------------------------------------------------------------------------------------------------------ |
| `hp`                   | Hit points of the entity.                                                                               |
| `materials_create_messages` | Whether damage events create messages (`1` for yes, `0` for no).                                        |
| `ragdoll_material`     | The material used for the ragdoll when the entity dies.                                                 |
| `ragdoll_filenames_file` | Path to a file listing the sprite filenames for the ragdoll.                                            |
| `blood_sprite_directional` | Path to the sprite file for directional blood splatters.                                                |
| `blood_sprite_large`   | Path to the sprite file for large blood splatters.                                                      |
| `air_needed`           | Whether the entity requires air to survive (`1` for yes, `0` for no).                                   |
| `damage_multipliers`   | Modifiers for specific damage types.                                                                    |
| `drill`                | Damage multiplier against drill damage.                                                                 |

### SpriteComponent

Determines the visual appearance of the entity.

| Attribute    | Description                                     |
| :----------- | :---------------------------------------------- |
| `image_file` | Path to the XML file defining the sprite frames. |
| `z_index`    | Determines the rendering order (lower is further back). |

### PathFindingComponent

Manages the entity's ability to navigate the game world.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `distance_to_reach_node_x` | Horizontal distance (in pixels) considered "close enough" to a path node. |
| `distance_to_reach_node_y` | Vertical distance (in pixels) considered "close enough" to a path node.   |
| `frames_to_get_stuck`   | Number of frames before the AI considers itself stuck.                   |
| `can_jump`              | Whether the entity can jump (`0` for no, `1` for yes).                   |

### CharacterPlatformingComponent

Handles the physics and movement related to character platforming.

| Attribute                               | Description                                                                                             |
| :-------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `accel_x`                               | Horizontal acceleration.                                                                                |
| `pixel_gravity`                         | The strength of gravity applied to the entity in pixels per frame.                                      |
| `jump_velocity_y`                       | The initial vertical velocity when jumping.                                                             |
| `run_velocity`                          | The maximum horizontal running speed.                                                                   |
| `velocity_min_y`                        | Minimum vertical velocity.                                                                              |
| `velocity_max_y`                        | Maximum vertical velocity.                                                                              |
| `run_animation_velocity_switching_enabled` | Whether the running animation can switch based on velocity (`1` for yes, `0` for no).                   |
| `run_animation_velocity_switching_threshold` | The velocity threshold at which the running animation switches.                                         |

### HitboxComponent

Defines the collision boundaries of the entity.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `aabb_min_x`   | Minimum X-coordinate of the Axis-Aligned Bounding Box (AABB).            |
| `aabb_max_x`   | Maximum X-coordinate of the AABB.                                        |
| `aabb_min_y`   | Minimum Y-coordinate of the AABB.                                        |
| `aabb_max_y`   | Maximum Y-coordinate of the AABB.                                        |

### CharacterDataComponent

Contains general character-specific data.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `climb_over_y`         | The maximum Y-difference the character can climb over.                   |
| `collision_aabb_min_x` | Minimum X-coordinate for collision detection.                            |
| `collision_aabb_max_x` | Maximum X-coordinate for collision detection.                            |
| `collision_aabb_min_y` | Minimum Y-coordinate for collision detection.                            |
| `collision_aabb_max_y` | Maximum Y-coordinate for collision detection.                            |
| `buoyancy_check_offset_y` | Offset for buoyancy checks.                                              |

### CameraBoundComponent

Controls how the camera behaves relative to the entity.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `max_count` | Maximum number of this entity type that can be active before camera effects. |
| `distance`  | The distance from the entity at which camera effects are triggered.      |