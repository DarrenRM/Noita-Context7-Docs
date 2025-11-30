---
title: Blood Crystal Physics Entity
category: entities
---

# Blood Crystal Physics Entity

This document details the `bloodcrystal_physics.xml` entity, which defines a flying, crystalline enemy in Noita. It focuses on its physics, AI, and combat-related attributes.

## Core Components

### PhysicsAIComponent
Manages the entity's movement and physical interactions.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the target vector for movement.                        |
| `force_coeff`             | Coefficient for applying force to movement.                              |
| `force_balancing_coeff`   | Coefficient for balancing forces.                                        |
| `force_max`               | Maximum force that can be applied.                                       |
| `torque_coeff`            | Coefficient for applying torque (rotational force).                      |
| `torque_balancing_coeff`  | Coefficient for balancing torques.                                       |
| `torque_max`              | Maximum torque that can be applied.                                      |
| `damage_deactivation_prob`| Probability of deactivating due to damage.                               |
| `damage_deactivation_time`| Minimum and maximum duration of deactivation after taking damage.        |

### PhysicsBodyComponent
Defines the physical properties of the entity's body.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `allow_sleep`           | Whether the body can enter a sleep state when inactive.                  |
| `angular_damping`       | Resistance to rotational movement.                                       |
| `fixed_rotation`        | Whether the entity's rotation is fixed.                                  |
| `is_bullet`             | Whether the entity behaves like a bullet.                                |
| `linear_damping`        | Resistance to linear movement.                                           |
| `on_death_leave_physics`| Whether the physics body remains after death.                            |

### PhysicsImageShapeComponent
Defines the visual shape and material of the entity based on an image.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `image_file`| Path to the image file used for the shape.                               |
| `material`  | The material assigned to this shape (e.g., `crystal_purple`).            |
| `offset_x`  | Horizontal offset for the image.                                         |
| `offset_y`  | Vertical offset for the image.                                           |

### LightComponent
Adds a light source to the entity.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `radius`  | The radius of the light.                                                 |
| `r`, `g`, `b` | RGB color values for the light.                                          |

## Base Enemy Attributes (`base_enemy_flying.xml`)

This entity inherits from `base_enemy_flying.xml`, gaining general flying enemy characteristics.

### AnimalAIComponent
Controls the entity's artificial intelligence and behavior.

| Attribute                   | Description                                                              |
| :-------------------------- | :----------------------------------------------------------------------- |
| `preferred_job`             | The AI's preferred job or role.                                          |
| `creature_detection_range_x`| Horizontal range for detecting creatures.                                |
| `creature_detection_range_y`| Vertical range for detecting creatures.                                  |
| `sense_creatures`           | Whether the AI actively senses creatures.                                |
| `needs_food`                | Whether the entity requires food.                                        |
| `attack_ranged_enabled`     | Whether ranged attacks are enabled.                                      |
| `attack_melee_enabled`      | Whether melee attacks are enabled.                                       |
| `can_fly`                   | Whether the entity can fly.                                              |
| `eye_offset_y`              | Vertical offset for the entity's "eyes" or detection point.              |

### DamageModelComponent
Defines the entity's health and how it takes damage.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `hp`                    | Hit points (health) of the entity.                                       |
| `ragdoll_material`      | Material used for the ragdoll upon death.                                |
| `blood_material`        | Material used for blood effects.                                         |
| `fire_probability_ignition`| Probability of igniting from fire damage.                                |
| `air_needed`            | Whether the entity requires air to survive.                              |

#### Damage Multipliers
Specific multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.5`      |
| `projectile`| `0.5`      |
| `explosion` | `1.0`      |
| `electricity`| `0.1`      |
| `ice`       | `2.0`      |
| `fire`      | `0`        |
| `holy`      | `1.2`      |

### PathFindingComponent
Handles pathfinding and navigation.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `distance_to_reach_node`| Distance threshold for reaching a pathfinding node.                      |
| `frames_to_get_stuck`   | Number of frames before the entity is considered stuck.                  |
| `can_jump`              | Whether the entity can jump.                                             |
| `can_fly`               | Whether the entity can fly.                                              |

### GenomeDataComponent
Defines genetic traits and ecological role.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `herd_id`       | Identifier for the entity's herd or group.                               |
| `food_chain_rank`| Position in the food chain.                                              |
| `is_predator`   | Whether the entity is a predator.                                        |

### CharacterPlatformingComponent
Defines movement parameters related to platforming.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `jump_velocity_y`| Vertical velocity applied when jumping.                                  |
| `run_velocity`  | Horizontal movement speed.                                               |

### HitboxComponent
Defines the collision area of the entity.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `aabb_max_x`| Maximum X-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_max_y`| Maximum Y-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_min_x`| Minimum X-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_min_y`| Minimum Y-coordinate of the Axis-Aligned Bounding Box.                   |

### CharacterDataComponent
General character data, including collision bounds and mass.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `collision_aabb_min_x`| Minimum X-coordinate for collision detection.                            |
| `collision_aabb_max_x`| Maximum X-coordinate for collision detection.                            |
| `collision_aabb_min_y`| Minimum Y-coordinate for collision detection.                            |
| `collision_aabb_max_y`| Maximum Y-coordinate for collision detection.                            |
| `mass`            | The mass of the entity.                                                  |

## Interaction and Scripting

### CollisionTriggerComponent
Detects collisions with other entities and triggers actions.

| Attribute                   | Description                                                              |
| :-------------------------- | :----------------------------------------------------------------------- |
| `width`, `height`, `radius` | Dimensions of the trigger area.                                          |
| `required_tag`              | Tag of entities that must collide to trigger the event.                  |
| `timer_for_destruction`     | Timer duration before destruction if triggered.                          |
| `destroy_this_entity`       | Whether this entity is destroyed when triggered.                         |

### LuaComponent
Allows execution of Lua scripts.

| Attribute                   | Description                                                              |
| :-------------------------- | :----------------------------------------------------------------------- |
| `script_collision_trigger_hit`| Path to the Lua script executed when the collision trigger is hit.       |

### AudioLoopComponent
Manages looping audio for the entity.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `file`        | Path to the audio bank file.                                             |
| `event_name`  | Name of the audio event to play.                                         |
| `set_speed_parameter`| Whether to set a speed parameter for the audio.                          |
| `auto_play`   | Whether the audio should play automatically.                             |