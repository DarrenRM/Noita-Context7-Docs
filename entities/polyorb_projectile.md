---
title: Polyorb Projectile
category: entities
---

# Polyorb Projectile

This document details the configuration of the "polyorb" projectile entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Entity Configuration

The `polyorb.xml` file defines a projectile with several key components that dictate its behavior, physics, and visual appearance.

### Entity Tags

These tags define the fundamental properties and interactions of the polyorb.

*   `mortal`: The entity can be destroyed.
*   `hittable`: The entity can be hit by other projectiles or attacks.
*   `homing_target`: The entity can be targeted by homing effects.
*   `polymorphable_NOT`: The entity cannot be polymorphed.
*   `glue_NOT`: The entity is not affected by glue.

### PhysicsAIComponent

Controls the movement and physics-based AI of the projectile.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the target vector for movement.                           |
| `force_coeff`             | Coefficient for applying force to steer the projectile.                     |
| `force_balancing_coeff`   | Coefficient for balancing forces to maintain stability.                     |
| `force_max`               | Maximum force that can be applied.                                          |
| `torque_coeff`            | Coefficient for applying torque for rotation.                               |
| `torque_balancing_coeff`  | Coefficient for balancing torque.                                           |
| `torque_max`              | Maximum torque that can be applied.                                         |
| `damage_deactivation_probability` | Probability that damage will deactivate the projectile.                     |
| `damage_deactivation_time_min` | Minimum time before damage can deactivate the projectile.                   |
| `damage_deactivation_time_max` | Maximum time before damage can deactivate the projectile.                   |

### PhysicsBodyComponent

Defines the physical properties of the projectile's body.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `allow_sleep`             | Whether the body can enter a sleeping state when inactive.                  |
| `angular_damping`         | Damping applied to angular velocity.                                        |
| `fixed_rotation`          | Whether the object's rotation is fixed.                                     |
| `is_bullet`               | Whether this is treated as a bullet for collision purposes.                 |
| `linear_damping`          | Damping applied to linear velocity.                                         |
| `force_add_update_areas`  | Whether to add update areas for forces.                                     |
| `on_death_leave_physics_body` | Whether to leave a physics body behind upon death.                          |

### PhysicsShapeComponent

Defines the collision shape of the projectile.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `is_circle`               | Whether the shape is a circle.                                              |
| `radius_x`                | Radius along the X-axis (if circle, same as `radius_y`).                    |
| `radius_y`                | Radius along the Y-axis (if circle, same as `radius_x`).                    |
| `friction`                | Friction coefficient of the shape.                                          |
| `restitution`             | Bounciness of the shape.                                                    |

## Base Enemy Configuration

The polyorb inherits properties from `base_enemy_basic.xml`, which provides a foundation for its AI and combat capabilities.

### DamageModelComponent

Defines the health and damage-related properties.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `hp`                      | Hit points of the projectile.                                               |
| `ragdoll_material`        | Material of the ragdoll when destroyed.                                     |
| `blood_material`          | Material of the blood/particles emitted on damage.                          |
| `ragdoll_fx_forced`       | Forced visual effect upon ragdoll creation.                                 |
| `fire_probability_of_ignition` | Probability of igniting from fire damage.                                   |
| `air_needed`              | Whether the entity requires air to survive.                                 |

#### Damage Multipliers

These multipliers affect how much damage the projectile takes from different sources.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `1.0`      |
| `projectile`| `1.0`      |
| `explosion` | `1.0`      |
| `electricity`| `0.1`      |
| `fire`      | `0`        |

### SpriteComponent

Defines the visual representation of the projectile.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `image_file`              | Path to the sprite's image definition file.                                 |
| `has_special_scale`       | Whether the sprite uses special scaling.                                    |
| `emissive`                | Whether the sprite emits light.                                             |
| `additive`                | Whether the sprite uses additive blending.                                  |
| `offset_x`                | X-axis offset for the sprite.                                               |
| `offset_y`                | Y-axis offset for the sprite.                                               |

### AnimalAIComponent

Configures the AI behavior, primarily for creature-like entities. While this is a projectile, some AI parameters are present.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `preferred_job`           | The preferred job for the AI.                                               |
| `attack_ranged_min_distance` | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance` | Maximum distance for ranged attacks.                                        |
| `creature_detection_range_x` | X-axis range for detecting creatures.                                       |
| `creature_detection_range_y` | Y-axis range for detecting creatures.                                       |
| `sense_creatures`         | Whether the AI senses creatures.                                            |
| `attack_ranged_enabled`   | Whether ranged attacks are enabled.                                         |
| `attack_melee_enabled`    | Whether melee attacks are enabled.                                          |
| `can_fly`                 | Whether the entity can fly.                                                 |
| `eye_offset_y`            | Vertical offset for the entity's "eyes" or detection point.                 |

### PathFindingComponent

Defines parameters related to pathfinding.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `distance_to_reach_node_x` | Distance to reach a node on the X-axis.                                     |
| `distance_to_reach_node_y` | Distance to reach a node on the Y-axis.                                     |
| `frames_to_get_stuck`     | Number of frames before the entity is considered stuck.                     |
| `can_jump`                | Whether the entity can jump.                                                |
| `can_fly`                 | Whether the entity can fly.                                                 |
| `jump_speed`              | Speed of jumping.                                                           |

### CharacterPlatformingComponent

Controls movement parameters related to platforming.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `jump_velocity_y`         | Vertical velocity applied when jumping.                                     |
| `run_velocity`            | Horizontal movement speed.                                                  |

### HitboxComponent

Defines the bounding box for hit detection.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `aabb_max_x`              | Maximum X-coordinate of the axis-aligned bounding box.                      |
| `aabb_max_y`              | Maximum Y-coordinate of the axis-aligned bounding box.                      |
| `aabb_min_x`              | Minimum X-coordinate of the axis-aligned bounding box.                      |
| `aabb_min_y`              | Minimum Y-coordinate of the axis-aligned bounding box.                      |

### CharacterDataComponent

General character data, including collision bounds.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `collision_aabb_min_x`    | Minimum X-coordinate for collision detection.                               |
| `collision_aabb_max_x`    | Maximum X-coordinate for collision detection.                               |
| `collision_aabb_min_y`    | Minimum Y-coordinate for collision detection.                               |
| `collision_aabb_max_y`    | Maximum Y-coordinate for collision detection.                               |

## Lua Components

These components execute Lua scripts to add custom behavior.

### LuaComponent (Death Script)

This component executes a script upon the projectile's removal or death.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `execute_on_removed`      | Whether to execute the script when the entity is removed.                   |
| `execute_every_n_frame`   | How often to execute the script (if not on removal).                        |
| `script_source_file`      | Path to the Lua script file.                                                |
| `remove_after_executed`   | Whether to remove the entity after the script executes.                     |

*   **Script:** `data/scripts/projectiles/polyorb_death.lua`
    *   This script is executed twice: once when the entity is removed, and again at a specific frame interval (220 frames) with `remove_after_executed="1"`, suggesting it handles cleanup or secondary effects.

## Particle Emitter Component

Defines the particles emitted by the polyorb.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the emitted particles.                                      |
| `gravity.y`               | Vertical gravity applied to particles.                                      |
| `lifetime_min`            | Minimum lifetime of emitted particles.                                      |
| `lifetime_max`            | Maximum lifetime of emitted particles.                                      |
| `count_min`               | Minimum number of particles emitted per burst.                              |
| `count_max`               | Maximum number of particles emitted per burst.                              |
| `render_on_grid`          | Whether particles are rendered on the game grid.                            |
| `fade_based_on_lifetime`  | Whether particles fade out based on their remaining lifetime.               |
| `area_circle_radius.max`  | Maximum radius of the circular emission area.                               |
| `cosmetic_force_create`   | Whether to create cosmetic particles.                                       |
| `airflow_force`           | Force applied by airflow.                                                   |
| `airflow_time`            | Duration of airflow effect.                                                 |
| `airflow_scale`           | Scale of the airflow effect.                                                |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                                  |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles.                                         |
| `x_vel_min`               | Minimum initial velocity on the X-axis.                                     |
| `x_vel_max`               | Maximum initial velocity on the X-axis.                                     |
| `y_vel_min`               | Minimum initial velocity on the Y-axis.                                     |
| `y_vel_max`               | Maximum initial velocity on the Y-axis.                                     |
| `is_emitting`             | Whether particle emission is currently active.                                |

## Audio Components

Defines the sound effects associated with the polyorb.

### AudioComponent

Plays a specific sound event.

*   **File:** `data/audio/Desktop/projectiles.bank`
*   **Event Root:** `projectiles/polymorph_bubble`

### AudioLoopComponent

Plays a looping sound event.

*   **File:** `data/audio/Desktop/projectiles.bank`
*   **Event Name:** `projectiles/magic_orb/loop`
*   **Auto Play:** `1` (enabled)