---
title: Gate Monster A (Boss Gate)
category: entities
---

# Gate Monster A (Boss Gate)

This document details the `gate_monster_a.xml` entity, representing a boss-type enemy found in Noita. It's designed to be a formidable opponent with unique physics and combat behaviors.

## Core Components

The Gate Monster A is built upon several foundational components that define its existence and interaction within the game world.

### PhysicsAIComponent

This component governs the creature's movement and AI-driven physics.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the vector used for targeting.                            |
| `force_coeff`             | Coefficient for applying force to movement.                                 |
| `force_balancing_coeff`   | Coefficient for balancing forces, likely for stability.                     |
| `force_max`               | Maximum force that can be applied.                                          |
| `torque_coeff`            | Coefficient for applying rotational force.                                  |
| `torque_balancing_coeff`  | Coefficient for balancing rotational forces.                                |
| `torque_max`              | Maximum torque that can be applied.                                         |
| `damage_deactivation_prob`| Probability of deactivating due to damage.                                  |
| `damage_deactivation_time`| Minimum and maximum duration of deactivation after taking damage.           |

### PhysicsBodyComponent

Defines the physical properties of the creature's body.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `allow_sleep`           | Whether the physics body can go to sleep.       |
| `angular_damping`       | Resistance to angular motion.                   |
| `fixed_rotation`        | Whether the rotation is fixed.                  |
| `is_bullet`             | If the body acts as a projectile.               |
| `linear_damping`        | Resistance to linear motion.                    |
| `on_death_leave_physics`| Whether the physics body remains after death.   |

### PhysicsImageShapeComponent

Defines the visual shape and collision properties based on an image.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `image_file`| Path to the image file used for the shape.      |
| `centered`  | Whether the image is centered.                  |
| `material`  | The material of the physics shape (e.g., rock). |
| `offset_x`  | X-axis offset for the image.                    |
| `offset_y`  | Y-axis offset for the image.                    |

### Base (Inherited from `base_enemy_flying.xml`)

This entity inherits core behaviors from `base_enemy_flying.xml`, providing common enemy functionalities.

#### AnimalAIComponent

Controls the creature's artificial intelligence and combat behavior.

| Attribute                   | Description                                                               |
| :-------------------------- | :------------------------------------------------------------------------ |
| `preferred_job`             | The creature's preferred AI job.                                          |
| `attack_ranged_min_distance`| Minimum distance for ranged attacks.                                      |
| `attack_ranged_max_distance`| Maximum distance for ranged attacks.                                      |
| `creature_detection_range_x`| X-axis range for detecting creatures.                                     |
| `creature_detection_range_y`| Y-axis range for detecting creatures.                                     |
| `attack_ranged_action_frame`| Frame at which a ranged attack is initiated.                              |
| `attack_melee_action_frame` | Frame at which a melee attack is initiated.                               |
| `sense_creatures`           | Whether the creature senses other creatures.                              |
| `attack_ranged_enabled`     | Whether ranged attacks are enabled.                                       |
| `attack_melee_enabled`      | Whether melee attacks are enabled.                                        |
| `can_fly`                   | Whether the creature can fly.                                             |
| `eye_offset_y`              | Vertical offset for the creature's eyes.                                  |
| `attack_ranged_offset_y`    | Vertical offset for ranged attack targeting.                              |

#### DamageModelComponent

Manages the creature's health, damage resistances, and how it reacts to damage.

| Attribute                 | Description                                                                 |
| :------------------------ | :------------------------------------------------------------------------ |
| `hp`                      | Hit points of the creature.                                               |
| `ragdoll_material`        | Material used for the ragdoll upon death.                                 |
| `blood_material`          | Material of the blood particles.                                          |
| `blood_spray_material`    | Material of the blood spray particles.                                    |
| `fire_probability_of_ignition`| Probability of igniting from fire damage.                               |
| `air_needed`              | Whether the creature requires air to survive.                             |
| `physics_objects_damage`  | Whether physics objects deal damage to this entity.                       |

##### damage_multipliers

Defines multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.1`      |
| `projectile`| `0.1`      |
| `explosion` | `1.2`      |
| `electricity`| `0`        |
| `fire`      | `0`        |
| `ice`       | `0`        |
| `radioactive`| `0`        |

#### PathFindingComponent

Handles pathfinding and movement logic for the creature.

| Attribute                 | Description                                     |
| :------------------------ | :---------------------------------------------- |
| `distance_to_reach_node_x`| X-axis distance to consider a node reached.     |
| `distance_to_reach_node_y`| Y-axis distance to consider a node reached.     |
| `frames_to_get_stuck`     | Frames before considering the creature stuck.   |
| `can_jump`                | Whether the creature can jump.                  |
| `can_fly`                 | Whether the creature can fly.                   |
| `jump_speed`              | Speed of jumping.                               |

#### GenomeDataComponent

Contains genetic information for creature behavior and classification.

| Attribute         | Description                                     |
| :---------------- | :---------------------------------------------- |
| `herd_id`         | Identifier for the creature's herd.             |
| `food_chain_rank` | Rank in the food chain.                         |
| `is_predator`     | Whether the creature is a predator.             |

#### CharacterPlatformingComponent

Defines platforming-related movement parameters.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `jump_velocity_y`| Vertical velocity applied when jumping.         |
| `run_velocity`  | Horizontal movement speed.                      |

#### HitboxComponent

Defines the bounding box for hit detection.

| Attribute    | Description                                     |
| :----------- | :---------------------------------------------- |
| `aabb_min_x` | Minimum X-coordinate of the bounding box.       |
| `aabb_max_x` | Maximum X-coordinate of the bounding box.       |
| `aabb_min_y` | Minimum Y-coordinate of the bounding box.       |
| `aabb_max_y` | Maximum Y-coordinate of the bounding box.       |

#### CharacterDataComponent

General character data, including collision and mass.

| Attribute                 | Description                                     |
| :------------------------ | :---------------------------------------------- |
| `collision_aabb_min_x`    | Minimum X-coordinate for collision.             |
| `collision_aabb_max_x`    | Maximum X-coordinate for collision.             |
| `collision_aabb_min_y`    | Minimum Y-coordinate for collision.             |
| `collision_aabb_max_y`    | Maximum Y-coordinate for collision.             |
| `mass`                    | Mass of the character.                          |

## Specific Components

These components add unique functionalities to the Gate Monster A.

### LuaComponent (Scripting)

This component allows for custom scripting to define specific behaviors.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `script_source_file`| Path to the Lua script file for general logic.  |
| `execute_every_n_frame`| How often the script logic is executed.       |
| `script_death`      | Path to the Lua script file for death logic.    |

### CellEaterComponent

Enables the creature to consume cells (materials) in its vicinity.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `eat_probability`| Probability of eating a cell.                   |
| `radius`    | The radius within which cells can be eaten.     |
| `ignored_material`| Materials that the creature will not eat.     |

### AreaDamageComponent

Applies damage to entities within a specified area.

| Attribute         | Description                                     |
| :---------------- | :---------------------------------------------- |
| `aabb_min.x`      | Minimum X-coordinate of the damage area.        |
| `aabb_min.y`      | Minimum Y-coordinate of the damage area.        |
| `aabb_max.x`      | Maximum X-coordinate of the damage area.        |
| `aabb_max.y`      | Maximum Y-coordinate of the damage area.        |
| `damage_per_frame`| Amount of damage dealt per frame.               |
| `update_every_n_frame`| How often the damage is applied.              |
| `entities_with_tag`| Tags of entities that will take damage.       |
| `damage_type`     | The type of damage dealt (e.g., CURSE).         |

### AudioComponent & AudioLoopComponent

Handle sound effects and looping audio for the creature.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `file`        | Path to the audio bank file.                    |
| `event_root`  | Root event name for general sounds.             |
| `event_name`  | Specific event name for looping sounds.         |
| `set_speed_parameter`| Whether to set speed parameter for loop.    |
| `auto_play`   | Whether the loop starts automatically.          |

### SpriteParticleEmitterComponent (Shadow)

Emits particles to create a shadow effect.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `sprite_file`       | Path to the sprite file for the particles.      |
| `delay`             | Delay before emission starts.                   |
| `lifetime`          | Lifetime of emitted particles.                  |
| `sprite_centered`   | Whether the sprite is centered.                 |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of particles. |
| `color_change.a`    | How the alpha color changes over time.          |
| `render_back`       | Whether to render particles behind the entity.  |
| `velocity.y`        | Vertical velocity of particles.                 |
| `gravity.y`         | Gravity applied to particles.                   |
| `scale.x`, `scale.y`| Initial scale of particles.                     |
| `additive`          | Whether to use additive blending.               |
| `emissive`          | Whether particles are emissive.                 |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Interval between particle emissions. |
| `count_min`, `count_max` | Number of particles emitted per interval.   |

### ParticleEmitterComponent (Ring)

Emits particles to create a visual ring effect.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `emitted_material_name` | Material of the emitted particles.              |
| `gravity.y`             | Gravity applied to particles.                   |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of particles.  |
| `x_pos_offset_min`, `x_pos_offset_max` | X-axis offset for emission. |
| `y_pos_offset_min`, `y_pos_offset_max` | Y-axis offset for emission. |
| `area_circle_radius.min`, `area_circle_radius.max` | Radius of the emission circle. |
| `count_min`, `count_max` | Number of particles emitted.                  |
| `render_on_grid`        | Whether to render particles on the grid.        |
| `collide_with_grid`     | Whether particles collide with the grid.        |
| `fade_based_on_lifetime`| Whether particles fade based on lifetime.       |
| `cosmetic_force_create` | Whether particles are cosmetic.                 |
| `airflow_force`, `airflow_time`, `airflow_scale` | Airflow parameters. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Interval between particle emissions. |
| `emit_cosmetic_particles`| Whether to emit cosmetic particles.           |
| `is_emitting`           | Whether particle emission is active.            |

### Entity (Protection)

A nested entity that grants a protective effect.

#### GameEffectComponent

Applies a game effect to the entity.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of game effect (e.g., PROTECTION_ELECTRICITY). |
| `frames`  | Duration of the effect (-1 for infinite).       |