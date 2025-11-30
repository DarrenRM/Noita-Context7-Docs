---
title: Base Robot Enemy Entity
category: entities
---

# Base Robot Enemy Entity

This document describes the core components and key attributes of a base robot enemy entity in Noita, intended for AI-assisted modding.

## Core Components

The `base_enemy_robot.xml` file defines a foundational robot enemy by inheriting from `base_humanoid.xml`. It primarily customizes AI, damage, visual, and movement behaviors.

### `AnimalAIComponent`

Controls the AI and behavior of the robot.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `creature_detection_range_x` | Horizontal range for detecting creatures.                                |
| `creature_detection_range_y` | Vertical range for detecting creatures.                                  |
| `attack_melee_damage_min` | Minimum damage dealt by melee attacks.                                   |
| `attack_melee_damage_max` | Maximum damage dealt by melee attacks.                                   |
| `food_material`           | The material this creature consumes for sustenance.                      |
| `needs_food`              | Whether the creature requires food to survive.                           |
| `sense_creatures`         | Whether the creature can sense other creatures.                          |
| `aggressiveness_min`      | Minimum aggressiveness level.                                            |
| `aggressiveness_max`      | Maximum aggressiveness level.                                            |

### `DamageModelComponent`

Defines the health, damage resistances, and how the robot reacts to damage and materials.

| Attribute                     | Description                                                                                             |
| :---------------------------- | :------------------------------------------------------------------------------------------------------ |
| `hp`                          | Hit points of the robot.                                                                                |
| `ragdoll_material`            | The material used for the robot's ragdoll upon death.                                                   |
| `blood_material`              | The material that acts as "blood" for this entity.                                                      |
| `blood_spray_material`        | The material used for blood spray particles.                                                            |
| `fire_probability_of_ignition`| Probability of igniting from fire damage.                                                               |
| `materials_that_damage`       | List of materials that inflict damage to the robot.                                                     |
| `materials_how_much_damage`   | Corresponding damage values for `materials_that_damage`.                                                |
| `air_needed`                  | Whether the entity requires air to survive.                                                             |

#### `damage_multipliers`

Specific multipliers for different damage types.

| Damage Type | Multiplier | Description                                                              |
| :---------- | :--------- | :----------------------------------------------------------------------- |
| `fire`      | `0.0`      | Immune to fire damage.                                                   |
| `drill`     | `0.1`      | Takes 10% damage from drills.                                            |
| `slice`     | `0.1`      | Takes 10% damage from slicing attacks.                                   |
| `melee`     | `0.3`      | Takes 30% damage from melee attacks.                                     |
| `projectile`| `0.5`      | Takes 50% damage from projectiles.                                       |
| `explosion` | `1.0`      | Takes normal damage from explosions.                                     |
| `electricity`| `2.0`      | Takes 200% damage from electricity.                                      |

### `SpriteComponent`

Determines the visual appearance of the robot.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `image_file`| Path to the sprite definition XML file.   |
| `z_index`   | Rendering order; lower values are further back. |

### `PathFindingComponent`

Defines how the robot navigates the game world.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `distance_to_reach_node_x` | Horizontal distance considered "close enough" to a pathfinding node. |
| `distance_to_reach_node_y` | Vertical distance considered "close enough" to a pathfinding node.   |
| `frames_to_get_stuck` | Number of frames before the AI considers itself stuck.                   |
| `can_jump`            | Whether the entity can jump to traverse obstacles.                       |

### `CharacterPlatformingComponent`

Governs the robot's movement physics and animations.

| Attribute                               | Description                                                              |
| :-------------------------------------- | :----------------------------------------------------------------------- |
| `accel_x`                               | Horizontal acceleration.                                                 |
| `pixel_gravity`                         | The strength of gravity applied to the entity in pixels per frame.       |
| `jump_velocity_y`                       | The vertical velocity applied when jumping.                              |
| `run_velocity`                          | The base running speed of the entity.                                    |
| `run_animation_velocity_switching_enabled` | Enables switching animations based on movement speed.                    |
| `run_animation_velocity_switching_threshold` | The speed threshold at which animation switching occurs.                 |

### `HitboxComponent`

Defines the bounding box used for collision detection and targeting.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `aabb_min_x`   | Minimum X-coordinate of the Axis-Aligned Bounding Box (AABB).            |
| `aabb_max_x`   | Maximum X-coordinate of the AABB.                                        |
| `aabb_min_y`   | Minimum Y-coordinate of the AABB.                                        |
| `aabb_max_y`   | Maximum Y-coordinate of the AABB.                                        |

### `CharacterDataComponent`

Provides general character-specific data and collision properties.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `climb_over_y`            | The maximum height the character can climb over.                         |
| `collision_aabb_min_x`    | Minimum X-coordinate for precise collision detection.                    |
| `collision_aabb_max_x`    | Maximum X-coordinate for precise collision detection.                    |
| `collision_aabb_min_y`    | Minimum Y-coordinate for precise collision detection.                    |
| `collision_aabb_max_y`    | Maximum Y-coordinate for precise collision detection.                    |
| `buoyancy_check_offset_y` | Vertical offset for buoyancy checks.                                     |

### `AudioComponent`

Manages the sound effects associated with the robot.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `file`       | Path to the audio bank file.                                             |
| `event_root` | The root event name for sounds related to this entity.                   |

## Key Attributes Summary

*   **Tags:** `teleportable_NOT`, `enemy`, `robot` - Essential for identifying and categorizing the entity.
*   **HP:** `0.5` - Very low health, making it a relatively weak enemy.
*   **Damage Multipliers:** Notably high `electricity` multiplier (`2.0`) and immunity to `fire` (`0.0`).
*   **Movement:** Standard platforming physics with `pixel_gravity` and `run_velocity`.
*   **AI:** Designed to sense creatures and exhibit aggressive behavior.
*   **Visuals:** Uses `data/enemies_gfx/zombie.xml` for its sprite, indicating a zombie-like appearance.
*   **Blood/Materials:** Uses `oil` as its blood material and is damaged by `acid`, `lava`, and `magic_liquid_mana_regeneration`.