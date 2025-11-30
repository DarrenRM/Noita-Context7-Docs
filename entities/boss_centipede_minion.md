---
title: Boss Centipede Minion
category: entities
---

# Boss Centipede Minion

This document details the `boss_centipede_minion.xml` entity, representing a smaller, flying enemy that accompanies the main boss centipede. It focuses on its AI, physics, combat capabilities, and visual components.

## Core Components

### PhysicsAIComponent
Manages the creature's movement and AI-driven physics.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the target vector for movement.                        |
| `force_coeff`             | Coefficient for applying force to movement.                              |
| `force_balancing_coeff`   | Coefficient for balancing forces during movement.                        |
| `force_max`               | Maximum force that can be applied.                                       |
| `torque_coeff`            | Coefficient for applying torque (rotational force).                      |
| `torque_balancing_coeff`  | Coefficient for balancing torques.                                       |
| `torque_max`              | Maximum torque that can be applied.                                      |
| `damage_deactivation_prob`| Probability (in %) that the AI deactivates upon taking damage.           |
| `damage_deactivation_time`| Minimum and maximum duration (in frames) the AI remains deactivated.     |

### PhysicsBodyComponent
Defines the physical properties of the minion's body.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `allow_sleep`             | Whether the physics body can enter a sleep state to save performance.    |
| `angular_damping`         | Resistance to rotational movement.                                       |
| `fixed_rotation`          | Whether the object's rotation is fixed.                                  |
| `is_bullet`               | If true, this object is treated as a projectile.                         |
| `linear_damping`          | Resistance to linear movement.                                           |
| `on_death_leave_physics_body` | If true, the physics body remains after the entity dies.                 |

### PhysicsImageShapeComponent
Defines the collision shape based on an image.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `image_file`| Path to the image used for the physics shape.                            |
| `material`  | The material of the physics shape (e.g., `meat_slime`).                  |
| `offset_x`  | X-axis offset for the shape relative to the entity's origin.             |
| `offset_y`  | Y-axis offset for the shape relative to the entity's origin.             |

### LightComponent
Adds a light source to the entity.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `radius`  | The radius of the light.                                                 |
| `r`, `g`, `b` | RGB color values for the light.                                          |

## Base Enemy Components (Inherited from `base_enemy_flying.xml`)

### AnimalAIComponent
Controls the creature's behavior and combat actions.

| Attribute                     | Description                                                              |
| :---------------------------- | :----------------------------------------------------------------------- |
| `preferred_job`               | The AI's preferred job (e.g., `JobDefault`).                             |
| `dont_counter_attack_own_herd`| Prevents counter-attacking members of its own herd.                      |
| `attack_ranged_min_distance`  | Minimum distance for ranged attacks.                                     |
| `attack_ranged_max_distance`  | Maximum distance for ranged attacks.                                     |
| `creature_detection_range_x`  | X-axis range for detecting creatures.                                    |
| `creature_detection_range_y`  | Y-axis range for detecting creatures.                                    |
| `attack_ranged_action_frame`  | The frame number when the ranged attack action is performed.             |
| `attack_melee_action_frame`   | The frame number when the melee attack action is performed.              |
| `sense_creatures`             | Whether the creature senses other creatures.                             |
| `attack_ranged_enabled`       | Enables ranged attacks.                                                  |
| `attack_melee_enabled`        | Enables melee attacks.                                                   |
| `can_fly`                     | Whether the creature can fly.                                              |
| `needs_food`                  | Whether the creature requires food.                                      |
| `attack_ranged_entity_file`   | The entity file used for ranged attacks (e.g., projectile).              |
| `attack_ranged_frames_between`| Number of frames between ranged attacks.                                 |
| `eye_offset_y`                | Y-axis offset for the creature's eyes.                                   |
| `attack_ranged_offset_y`      | Y-axis offset for the ranged attack origin.                              |

### DamageModelComponent
Defines the entity's health and damage properties.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `hp`                      | Hit points of the entity.                                                |
| `ragdoll_material`        | Material used for the ragdoll upon death.                                |
| `blood_material`          | Material of the blood splatters.                                         |
| `blood_sprite_directional`| Particle effect for directional blood splatters.                         |
| `blood_sprite_large`      | Particle effect for large blood splatters.                               |

#### damage_multipliers
Defines multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.3`      |
| `projectile`| `0.3`      |
| `explosion` | `0.8`      |
| `electricity`| `0.1`      |
| `fire`      | `0`        |

### SpriteComponent
Defines the visual sprite for the entity.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `image_file`      | Path to the sprite image.                                                |
| `offset_x`, `offset_y` | Offsets for the sprite's position.                                       |
| `has_special_scale`| Whether special scaling is applied.                                      |

### PathFindingGridMarkerComponent
Marks the entity for pathfinding grid usage.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `marker_work_flag` | A flag used by the pathfinding system.                                   |

### PathFindingComponent
Handles pathfinding logic for the entity.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `distance_to_reach_node_x` | X-axis distance to consider a node reached.                              |
| `distance_to_reach_node_y` | Y-axis distance to consider a node reached.                              |
| `frames_to_get_stuck` | Number of frames before the entity is considered stuck.                  |
| `can_jump`            | Whether the entity can jump.                                             |
| `can_fly`             | Whether the entity can fly.                                              |

### GenomeDataComponent
Defines genetic properties, influencing AI and interactions.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `herd_id`       | Identifier for the creature's herd.                                      |
| `food_chain_rank`| Rank in the food chain.                                                  |
| `is_predator`   | Whether the creature is a predator.                                      |

### CharacterPlatformingComponent
Handles character-specific movement like running and jumping.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `jump_velocity_y`| Vertical velocity applied when jumping.                                  |
| `run_velocity`  | Horizontal movement speed.                                               |

### HitboxComponent
Defines the entity's hitbox for interactions.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `aabb_max_x`| Maximum X-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_max_y`| Maximum Y-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_min_x`| Minimum X-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_min_y`| Minimum Y-coordinate of the Axis-Aligned Bounding Box.                   |

### CameraBoundComponent
Controls how the entity interacts with the camera's bounds.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `max_count` | Maximum number of this entity that can be active within camera bounds.   |
| `distance`  | Distance from the camera that affects entity behavior.                   |

### CharacterDataComponent
General character data, including collision properties.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `collision_aabb_min_x`| Minimum X-coordinate for collision detection.                            |
| `collision_aabb_max_x`| Maximum X-coordinate for collision detection.                            |
| `collision_aabb_min_y`| Minimum Y-coordinate for collision detection.                            |
| `collision_aabb_max_y`| Maximum Y-coordinate for collision detection.                            |
| `mass`              | The mass of the character.                                               |

## Other Components

### SpriteParticleEmitterComponent
Responsible for emitting particles, likely for visual effects.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `sprite_file`           | The sprite file used for emitted particles.                              |
| `lifetime`              | Duration of each emitted particle.                                       |
| `color_change`          | How the color of particles changes over their lifetime.                  |
| `velocity`              | Initial velocity of emitted particles.                                   |
| `gravity`               | Gravity applied to emitted particles.                                    |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                               |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                               |
| `count_min`, `count_max`| Minimum and maximum number of particles emitted per interval.            |

### Verlet Chains (Tentacles)
The entity includes multiple instances of `minion_tentacle.xml`, attached via `InheritTransformComponent` to form its body. These likely represent its segmented tentacles.

*   `data/entities/animals/boss_centipede/verlet_chains/minion_tentacle.xml` is instantiated three times with different positional offsets.