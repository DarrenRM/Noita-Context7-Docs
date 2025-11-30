---
title: Book Physics Entity
category: entities
---

# Book Physics Entity

This document details the `book_physics.xml` entity, which defines a flying, physics-driven enemy with a focus on its physical interactions and AI behavior.

## Core Components

This entity is built upon several key components that dictate its behavior and appearance.

### PhysicsAIComponent

Controls the AI's physical movement and reactions.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the target vector for movement.                        |
| `force_coeff`             | Coefficient for applying force to movement.                              |
| `force_balancing_coeff`   | Coefficient for balancing applied forces.                                |
| `force_max`               | Maximum force that can be applied.                                       |
| `torque_coeff`            | Coefficient for applying torque (rotational force).                      |
| `torque_balancing_coeff`  | Coefficient for balancing applied torques.                               |
| `torque_max`              | Maximum torque that can be applied.                                      |
| `damage_deactivation_prob`| Probability of deactivating due to damage.                               |
| `damage_deactivation_time_min` | Minimum time before deactivation after taking damage.                  |
| `damage_deactivation_time_max` | Maximum time before deactivation after taking damage.                  |

### PhysicsBodyComponent

Defines the physical properties of the entity's body.

| Attribute               | Description                                    |
| :---------------------- | :--------------------------------------------- |
| `allow_sleep`           | Whether the body can enter a sleep state.      |
| `angular_damping`       | Damping effect on rotational movement.         |
| `fixed_rotation`        | Whether the body's rotation is fixed.          |
| `is_bullet`             | Whether the body behaves like a bullet.         |
| `linear_damping`        | Damping effect on linear movement.             |
| `on_death_leave_physics_body` | Whether to leave a physics body upon death. |

### PhysicsImageShapeComponent

Defines the entity's shape based on an image file.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `image_file`| Path to the image file used for shape.    |
| `centered`  | Whether the image is centered.            |
| `material`  | The material of the physics shape.        |

### MaterialInventoryComponent

Manages the materials contained within the entity and their leakage behavior.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `_enabled`              | Whether the component is active.                                         |
| `drop_as_item`          | Whether to drop materials as items on death.                             |
| `on_death_spill`        | Whether to spill materials on death.                                     |
| `leak_pressure_min`     | Minimum pressure at which materials leak.                                |
| `leak_pressure_max`     | Maximum pressure at which materials leak.                                |
| `leak_on_damage_percent`| Percentage of damage at which leakage occurs.                            |
| `b2_force_on_leak`      | Force applied when leaking.                                              |

#### `count_per_material_type`

Specifies the amount of each material contained.

| Material | Count |
| :------- | :---- |
| `oil`    | 200   |

### ExplodeOnDamageComponent

Handles the entity's explosion behavior when damaged or upon death.

| Attribute                       | Description                                                              |
| :------------------------------ | :----------------------------------------------------------------------- |
| `explode_on_death_percent`      | Percentage of health at which explosion occurs on death.                 |
| `explode_on_damage_percent`     | Percentage of damage at which explosion occurs.                          |
| `physics_body_modified_death_prob`| Probability of physics body modification upon death.                     |
| `physics_body_destruction_req`  | Required destruction level for physics body modification.                |

#### `config_explosion`

Configuration for the explosion effect.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `damage`                  | Damage dealt by the explosion.                                           |
| `camera_shake`            | Intensity of camera shake during explosion.                              |
| `explosion_radius`        | Radius of the explosion.                                                 |
| `explosion_sprite`        | Path to the sprite for the explosion effect.                             |
| `explosion_sprite_lifetime`| Lifetime of the explosion sprite.                                        |
| `create_cell_probability` | Probability of creating cells during explosion.                          |
| `hole_destroy_liquid`     | Whether the explosion destroys liquids.                                  |
| `hole_enabled`            | Whether holes are created by the explosion.                              |
| `ray_energy`              | Energy of rays emitted by the explosion.                                 |
| `particle_effect`         | Whether particle effects are enabled.                                    |
| `damage_mortals`          | Whether the explosion damages mortals.                                   |
| `physics_explosion_power.min`| Minimum physics force applied by the explosion.                          |
| `physics_explosion_power.max`| Maximum physics force applied by the explosion.                          |
| `physics_throw_enabled`   | Whether physics objects are thrown by the explosion.                     |
| `shake_vegetation`        | Whether vegetation is shaken by the explosion.                           |
| `sparks_count_min`        | Minimum number of sparks created.                                        |
| `sparks_count_max`        | Maximum number of sparks created.                                        |
| `sparks_enabled`          | Whether sparks are enabled.                                              |
| `stains_enabled`          | Whether stains are created by the explosion.                             |
| `stains_radius`           | Radius of the stains created.                                            |

### LightComponent

Defines the light emitted by the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `radius`  | Radius of the light.                      |
| `r`       | Red component of the light color.         |
| `g`       | Green component of the light color.       |
| `b`       | Blue component of the light color.        |

## Base Enemy Robot Properties

This entity inherits properties from `base_enemy_robot.xml`, providing common enemy functionalities.

### AnimalAIComponent

Defines the AI behavior of the creature.

| Attribute                   | Description                                                              |
| :-------------------------- | :----------------------------------------------------------------------- |
| `preferred_job`             | The preferred job for this AI.                                           |
| `creature_detection_range_x`| Horizontal range for detecting creatures.                                |
| `creature_detection_range_y`| Vertical range for detecting creatures.                                  |
| `attack_ranged_min_distance`| Minimum distance for ranged attacks.                                     |
| `attack_ranged_max_distance`| Maximum distance for ranged attacks.                                     |
| `food_material`             | The material this creature considers food.                               |
| `needs_food`                | Whether the creature requires food.                                      |
| `sense_creatures`           | Whether the creature senses other creatures.                             |
| `attack_ranged_enabled`     | Whether ranged attacks are enabled.                                      |
| `attack_melee_enabled`      | Whether melee attacks are enabled.                                       |
| `attack_ranged_offset_y`    | Vertical offset for ranged attacks.                                      |
| `can_fly`                   | Whether the creature can fly.                                            |
| `can_walk`                  | Whether the creature can walk.                                           |
| `attack_ranged_entity_file` | Path to the entity file used for ranged attacks.                         |
| `attack_ranged_frames_between`| Frames between ranged attacks.                                           |

### DamageModelComponent

Manages the entity's health and damage-related properties.

| Attribute                   | Description                                                              |
| :-------------------------- | :----------------------------------------------------------------------- |
| `hp`                        | Health points of the entity.                                             |
| `fire_probability_of_ignition`| Probability of igniting from fire.                                       |

### SpriteComponent

Defines the visual appearance of the entity.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `image_file`        | Path to the sprite's image file.                                         |
| `rect_animation`    | The current rectangle animation state.                                   |
| `next_rect_animation`| The next rectangle animation state.                                      |
| `special_scale_x`   | Special scaling factor for the x-axis.                                   |
| `has_special_scale` | Whether special scaling is applied.                                      |
| `emissive`          | Whether the sprite is emissive (glows).                                  |
| `additive`          | Whether the sprite uses additive blending.                               |
| `offset_x`          | Horizontal offset of the sprite.                                         |
| `offset_y`          | Vertical offset of the sprite.                                           |

### PathFindingComponent

Defines the pathfinding capabilities of the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `can_walk`| Whether the entity can walk.              |
| `can_fly` | Whether the entity can fly.               |

### PathFindingGridMarkerComponent

Marks the entity's presence on the pathfinding grid.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `marker_work_flag`| The flag used to mark its position.       |

### GenomeDataComponent

Contains genetic information for the entity.

| Attribute         | Description                               |
| :---------------- | :---------------------------------------- |
| `herd_id`         | The ID of the herd this entity belongs to.|
| `food_chain_rank` | The entity's rank in the food chain.      |
| `is_predator`     | Whether the entity is a predator.         |

### CharacterPlatformingComponent

Handles character movement, including jumping and flying.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `jump_velocity_y`   | Vertical velocity applied when jumping.                                  |
| `run_velocity`      | Horizontal velocity when running.                                        |
| `fly_speed_max_up`  | Maximum upward flying speed.                                             |
| `fly_speed_max_down`| Maximum downward flying speed.                                           |
| `fly_speed_mult`    | Multiplier for flying speed.                                             |
| `fly_speed_change_spd`| Speed at which flying speed changes.                                     |
| `fly_velocity_x`    | Horizontal velocity when flying.                                         |

### HitboxComponent

Defines the collision hitbox of the entity.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `aabb_min_x`| Minimum x-coordinate of the AABB.         |
| `aabb_max_x`| Maximum x-coordinate of the AABB.         |
| `aabb_min_y`| Minimum y-coordinate of the AABB.         |
| `aabb_max_y`| Maximum y-coordinate of the AABB.         |

### CameraBoundComponent

Manages how the entity interacts with the camera's bounds.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `max_count` | Maximum number of entities of this type.  |
| `distance`  | Distance from the camera.                 |

### SpriteStainsComponent

Handles sprite stains, if enabled.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_enabled`| Whether sprite stains are enabled.        |

### LuaComponent

Allows for custom Lua scripting to extend entity behavior.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `execute_every_n_frame`| How often the script is executed (in frames).                            |
| `script_source_file`| Path to the Lua script file.                                             |