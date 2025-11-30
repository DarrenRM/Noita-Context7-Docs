---
title: Ant Entity
category: entities
---

# Ant Entity

This document details the `ant.xml` entity file, providing key attributes for AI-assisted modding of the Ant creature in Noita.

## Core Components

The Ant entity is built upon several core components, each defining specific behaviors and properties.

### AnimalAIComponent

This component governs the Ant's artificial intelligence, including its combat, movement, and sensory capabilities.

| Attribute                       | Description                                                                 |
| :------------------------------ | :-------------------------------------------------------------------------- |
| `preferred_job`                 | Sets the default job for the AI (e.g., `JobDefault`).                       |
| `escape_if_damaged_probability` | Chance (in %) for the ant to flee when damaged.                             |
| `attack_melee_damage_min`       | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`       | Maximum damage dealt by melee attacks.                                      |
| `attack_melee_max_distance`     | Maximum distance for melee attacks.                                         |
| `attack_ranged_min_distance`    | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance`    | Maximum distance for ranged attacks.                                        |
| `creature_detection_range_x`    | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | Vertical range for detecting creatures.                                     |
| `attack_melee_action_frame`     | Animation frame at which melee attack is executed.                          |
| `attack_ranged_action_frame`    | Animation frame at which ranged attack is executed.                         |
| `food_material`                 | The type of material the ant consumes for sustenance.                       |
| `needs_food`                    | Whether the ant requires food to survive.                                   |
| `sense_creatures`               | Whether the ant can detect other creatures.                                 |
| `attack_ranged_enabled`         | Enables or disables ranged attacks.                                         |
| `attack_melee_enabled`          | Enables or disables melee attacks.                                          |
| `can_fly`                       | Whether the ant can fly.                                                    |
| `attack_ranged_entity_file`     | Path to the entity file used for ranged attacks (e.g., projectile).         |
| `attack_ranged_frames_between`  | Number of animation frames between ranged attacks.                          |

### DamageModelComponent

Defines the Ant's health, damage resistances, and how it reacts to damage.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `hp`                          | Hit points of the ant.                                                      |
| `ragdoll_material`            | Material used for the ragdoll when the ant dies.                            |
| `ragdoll_filenames_file`      | Path to a file listing ragdoll sprite filenames.                            |
| `blood_material`              | The material of the blood sprayed when damaged.                             |
| `blood_spray_material`        | The material of the blood spray effect.                                     |
| `fire_probability_of_ignition`| Chance (in %) for the ant to ignite when exposed to fire.                   |
| `materials_that_damage`       | List of materials that inflict damage to the ant.                           |
| `materials_how_much_damage`   | Corresponding damage values for each material in `materials_that_damage`.   |
| `air_lack_of_damage`          | Damage taken per second when in an environment without air.                 |
| `air_needed`                  | Whether the ant requires air to survive.                                    |
| `blood_sprite_directional`    | Path to the sprite file for directional blood splatters.                    |
| `blood_sprite_large`          | Path to the sprite file for large blood splatters.                          |

### SpriteComponent

Handles the visual representation of the Ant.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `image_file`| Path to the sprite image file.            |
| `offset_x`  | Horizontal offset for the sprite.         |
| `offset_y`  | Vertical offset for the sprite.           |

### PathFindingComponent

Manages the Ant's pathfinding and movement capabilities.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `distance_to_reach_node_x`    | Horizontal distance considered "close enough" to a pathfinding node.        |
| `distance_to_reach_node_y`    | Vertical distance considered "close enough" to a pathfinding node.          |
| `frames_to_get_stuck`         | Number of frames before the ant is considered stuck.                        |
| `can_jump`                    | Whether the ant can jump.                                                   |
| `jump_speed`                  | The speed at which the ant jumps.                                           |
| `initial_jump_lob`            | Controls the arc of the initial jump.                                       |
| `initial_jump_max_distance_x` | Maximum horizontal distance the ant can jump.                               |
| `initial_jump_max_distance_y` | Maximum vertical distance the ant can jump.                                 |

### CharacterPlatformingComponent

Defines the Ant's basic platforming movement parameters.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `jump_velocity_y` | Initial vertical velocity when jumping. |
| `run_velocity`    | Horizontal movement speed.                |

### HitboxComponent

Defines the bounding box used for collision detection.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `aabb_max_x`| Maximum X-coordinate of the hitbox.       |
| `aabb_max_y`| Maximum Y-coordinate of the hitbox.       |
| `aabb_min_x`| Minimum X-coordinate of the hitbox.       |
| `aabb_min_y`| Minimum Y-coordinate of the hitbox.       |

### CharacterDataComponent

Contains general character data, including collision properties and mass.

| Attribute             | Description                               |
| :-------------------- | :---------------------------------------- |
| `collision_aabb_min_x`| Minimum X-coordinate for collision.       |
| `collision_aabb_max_x`| Maximum X-coordinate for collision.       |
| `collision_aabb_min_y`| Minimum Y-coordinate for collision.       |
| `collision_aabb_max_y`| Maximum Y-coordinate for collision.       |
| `mass`                | The mass of the character.                |