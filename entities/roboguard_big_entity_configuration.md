---
title: Roboguard Big Entity Configuration
category: entities
---

# Roboguard Big Entity Configuration

This document details the configuration for the `roboguard_big` entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Core Entity Structure

The `roboguard_big` entity inherits from `base_enemy_robot.xml`, indicating it shares fundamental robot enemy characteristics.

## Key Components and Attributes

### AnimalAIComponent

This component governs the AI behavior of the Roboguard Big.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | Default job assigned to the AI.                                             |
| `attack_melee_damage_min`     | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`     | Maximum damage dealt by melee attacks.                                      |
| `creature_detection_range_x`  | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | Vertical range for detecting creatures.                                     |
| `food_material`               | Material the creature consumes (if `needs_food` is enabled).                |
| `needs_food`                  | Whether the creature requires food to survive.                              |
| `sense_creatures`             | Whether the creature can detect other creatures.                            |
| `attack_ranged_enabled`       | Enables ranged attacks.                                                     |
| `attack_ranged_entity_file`   | Path to the entity file for the ranged projectile.                          |
| `attack_ranged_frames_between`| Frames between consecutive ranged attacks.                                  |
| `attack_melee_action_frame`   | The frame on which a melee attack is executed.                              |
| `aggressiveness_min`          | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | Maximum aggressiveness level.                                               |
| `attack_ranged_offset_x`      | Horizontal offset for ranged attacks.                                       |
| `attack_ranged_min_distance`  | Minimum distance required for ranged attacks.                               |
| `attack_melee_max_distance`   | Maximum distance for melee attacks.                                         |

### DamageModelComponent

Defines the health and damage resistance properties of the entity.

| Attribute                   | Description                                                                 |
| :-------------------------- | :-------------------------------------------------------------------------- |
| `hp`                        | Hit points of the entity.                                                   |
| `ragdoll_material`          | Material used for the ragdoll when the entity is destroyed.                 |
| `ragdoll_filenames_file`    | Path to the file containing ragdoll sprite filenames.                       |
| `blood_material`            | Material that acts as "blood" for this entity.                              |
| `fire_probability_of_ignition`| Probability of igniting from fire damage.                                   |
| `damage_multipliers`        | Modifiers for damage taken from different sources.                          |

#### Damage Multipliers

| Type        | Multiplier | Description                                     |
| :---------- | :--------- | :---------------------------------------------- |
| `projectile`| `0.0`      | Immunity to projectile damage.                  |

### SpriteComponent

Controls the visual appearance of the entity.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `image_file`  | Path to the primary sprite image file.          |
| `offset_x`    | Horizontal offset for the sprite.               |
| `offset_y`    | Vertical offset for the sprite.                 |

### PathFindingComponent

Manages the entity's navigation and movement capabilities.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `distance_to_reach_node_x`| Horizontal distance to consider a node reached. |
| `distance_to_reach_node_y`| Vertical distance to consider a node reached.   |
| `frames_to_get_stuck`   | Frames before AI considers itself stuck.        |
| `can_jump`              | Whether the entity can jump.                    |

### CharacterPlatformingComponent

Defines parameters related to platforming and movement physics.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `swim_idle_buoyancy_coeff`| Buoyancy coefficient when idle in water.        |
| `jump_velocity_y`     | Vertical velocity applied when jumping.         |
| `run_velocity`        | Horizontal movement speed.                      |

### HitboxComponent

Defines the collision area for the entity.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `aabb_max_x`  | Maximum X-coordinate of the bounding box.       |
| `aabb_max_y`  | Maximum Y-coordinate of the bounding box.       |
| `aabb_min_x`  | Minimum X-coordinate of the bounding box.       |
| `aabb_min_y`  | Minimum Y-coordinate of the bounding box.       |

### CharacterDataComponent

General character properties, including collision and mass.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `collision_aabb_min_x`| Minimum X-coordinate for collision detection.   |
| `collision_aabb_max_x`| Maximum X-coordinate for collision detection.   |
| `collision_aabb_min_y`| Minimum Y-coordinate for collision detection.   |
| `collision_aabb_max_y`| Maximum Y-coordinate for collision detection.   |
| `mass`                | Mass of the character.                          |

### Additional Components

*   **ItemPickUpperComponent**: Indicates the entity can pick up items.
*   **GameEffectComponent**: Grants immunity to freezing (`PROTECTION_FREEZE`).
*   **SpriteComponent (Emissive)**: Defines an emissive sprite for visual effects.

This configuration provides a foundation for understanding and modifying the Roboguard Big's behavior and appearance.