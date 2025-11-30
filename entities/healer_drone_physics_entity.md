---
title: Healer Drone Physics Entity
category: entities
---

# Healer Drone Physics Entity

This document details the `healerdrone_physics.xml` entity, which defines the behavior and properties of the Healer Drone in Noita. This entity is designed to be a flying, support-oriented robot that can heal allies.

## Core Components

The Healer Drone is built upon several key components that dictate its physics, AI, and visual representation.

### PhysicsAIComponent

This component governs the drone's movement and physical interactions.

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the vector used to steer the drone towards its target.                                   |
| `force_coeff`             | Coefficient for applying directional forces to the drone.                                                  |
| `force_balancing_coeff`   | Coefficient for balancing forces to maintain stability.                                                    |
| `force_max`               | Maximum force that can be applied to the drone.                                                            |
| `torque_coeff`            | Coefficient for applying rotational forces (torque).                                                       |
| `torque_balancing_coeff`  | Coefficient for balancing torque to maintain rotational stability.                                         |
| `torque_max`              | Maximum torque that can be applied to the drone.                                                           |
| `damage_deactivation_prob`| Probability (in percent) that the drone will deactivate upon taking damage.                                |
| `damage_deactivation_time_min` | Minimum duration (in frames) the drone remains deactivated after taking damage.                            |
| `damage_deactivation_time_max` | Maximum duration (in frames) the drone remains deactivated after taking damage.                            |

### PhysicsBodyComponent

Defines the fundamental physics properties of the drone's body.

| Attribute               | Description                                                                                                |
| :---------------------- | :--------------------------------------------------------------------------------------------------------- |
| `allow_sleep`           | If set to 1, the physics body can enter a sleep state when inactive to save performance.                   |
| `angular_damping`       | Reduces the drone's rotational velocity over time.                                                         |
| `fixed_rotation`        | If set to 1, the drone's rotation is locked.                                                               |
| `is_bullet`             | If set to 1, the physics body is treated as a projectile.                                                  |
| `linear_damping`        | Reduces the drone's linear velocity over time.                                                             |
| `on_death_leave_physics_body` | If set to 1, the physics body remains in the world after the entity dies.                                  |

### PhysicsImageShapeComponent

Defines the visual shape and collision properties based on an image.

| Attribute    | Description                                                                                                |
| :----------- | :--------------------------------------------------------------------------------------------------------- |
| `image_file` | Path to the image file used for the drone's sprite and collision shape.                                    |
| `centered`   | If set to 1, the image is centered on the entity's origin.                                                 |
| `material`   | The material type associated with this physics shape, affecting interactions with other physics objects.     |

### MaterialInventoryComponent

Manages the materials contained within the drone, particularly for leakage upon damage.

| Attribute                | Description                                                                                                |
| :----------------------- | :--------------------------------------------------------------------------------------------------------- |
| `_enabled`               | Whether this component is active.                                                                          |
| `drop_as_item`           | If set to 1, the materials are dropped as an item upon death.                                              |
| `on_death_spill`         | If set to 1, materials will spill out upon death.                                                          |
| `leak_pressure_min`      | Minimum pressure at which materials will leak.                                                             |
| `leak_pressure_max`      | Maximum pressure at which materials will leak.                                                             |
| `leak_on_damage_percent` | The percentage of damage that must be sustained for leakage to occur.                                      |
| `b2_force_on_leak`       | Force applied to the physics body when materials leak.                                                     |
| `count_per_material_type`| Defines the types and amounts of materials contained.                                                      |
| `Material material="oil"`| Specifies the material type (e.g., "oil") and its count.                                                 |

### ExplodeOnDamageComponent

Handles the drone's explosion behavior when damaged or destroyed.

| Attribute                       | Description                                                                                                |
| :------------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `explode_on_death_percent`      | Percentage of HP remaining when the entity explodes upon death.                                            |
| `explode_on_damage_percent`     | Percentage of damage that triggers an explosion.                                                           |
| `physics_body_modified_death_prob`| Probability that the physics body is modified upon death.                                                  |
| `physics_body_destruction_req`  | The required destruction level of the physics body to trigger an explosion.                                |
| `config_explosion`              | Nested configuration for the explosion effect.                                                             |
| `damage`                        | Damage dealt by the explosion.                                                                             |
| `camera_shake`                  | Intensity of camera shake caused by the explosion.                                                         |
| `explosion_radius`              | Radius of the explosion.                                                                                   |
| `explosion_sprite`              | Path to the particle effect used for the explosion.                                                        |
| `create_cell_probability`       | Probability of creating cells (e.g., liquid) from the explosion.                                           |
| `hole_enabled`                  | If set to 1, the explosion creates holes in the environment.                                               |
| `ray_energy`                    | Energy of the explosion's rays.                                                                            |
| `physics_explosion_power.max`   | Maximum power of the physics-based explosion force.                                                        |
| `shake_vegetation`              | If set to 1, the explosion shakes vegetation.                                                              |
| `sparks_count_min`/`max`        | Minimum and maximum number of sparks generated by the explosion.                                           |
| `stains_enabled`                | If set to 1, the explosion leaves stains on the environment.                                               |
| `stains_radius`                 | Radius of the stains left by the explosion.                                                                |

### LightComponent

Adds a light source to the entity.

| Attribute | Description                                                                                                |
| :-------- | :--------------------------------------------------------------------------------------------------------- |
| `radius`  | The radius of the light emitted.                                                                           |
| `r`, `g`, `b` | RGB values defining the color of the light.                                                                |

## Base Enemy Robot Configuration

The Healer Drone inherits many properties from `base_enemy_robot.xml`, with specific overrides for its AI and appearance.

### AnimalAIComponent

This component defines the drone's artificial intelligence and behavior.

| Attribute                       | Description                                                                                                |
| :------------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `escape_if_damaged_probability` | Probability (in percent) that the drone will attempt to escape when damaged.                               |
| `tries_to_ranged_attack_friends`| If set to 1, the drone will attempt to ranged attack its allies.                                           |
| `preferred_job`                 | The primary job assigned to this AI (e.g., "JobDefault").                                                  |
| `creature_detection_range_x`/`y`| The range (in pixels) for detecting creatures horizontally and vertically.                                 |
| `attack_ranged_min_distance`    | Minimum distance from which the drone will attempt ranged attacks.                                         |
| `attack_ranged_max_distance`    | Maximum distance from which the drone will attempt ranged attacks.                                         |
| `food_material`                 | The material the creature considers food (though `needs_food` is 0 here).                                  |
| `needs_food`                    | If set to 1, the creature requires food to survive.                                                        |
| `sense_creatures`               | If set to 1, the creature can sense other creatures.                                                       |
| `attack_ranged_enabled`         | If set to 1, ranged attacks are enabled.                                                                   |
| `attack_melee_enabled`          | If set to 1, melee attacks are enabled.                                                                    |
| `can_fly`                       | If set to 1, the drone can fly.                                                                            |
| `can_walk`                      | If set to 1, the drone can walk.                                                                           |
| `attack_ranged_offset_x`/`y`    | Offset from the drone's position when performing a ranged attack.                                          |
| `attack_ranged_entity_file`     | Path to the entity file for the projectile used in ranged attacks.                                         |
| `attack_ranged_frames_between`  | Minimum frames between ranged attacks.                                                                     |
| `aggressiveness_min`/`max`      | Minimum and maximum aggressiveness level.                                                                  |

### DamageModelComponent

Defines the health and damage-related properties of the drone.

| Attribute                     | Description                                                                                                |
| :---------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `hp`                          | The hit points of the drone.                                                                               |
| `fire_probability_of_ignition`| Probability (in percent) of igniting from fire.                                                            |

### SpriteComponent

Controls the visual appearance and animations of the drone.

| Attribute           | Description                                                                                                |
| :------------------ | :--------------------------------------------------------------------------------------------------------- |
| `image_file`        | Path to the image file for the drone's sprite.                                                             |
| `rect_animation`    | The name of the current rectangle animation.                                                               |
| `next_rect_animation`| The name of the next rectangle animation to transition to.                                                 |
| `emissive`          | If set to 1, the sprite emits light.                                                                       |
| `additive`          | If set to 1, the sprite uses additive blending.                                                            |

### PathFindingComponent

Determines how the drone navigates the game world.

| Attribute                   | Description                                                                                                |
| :-------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `can_walk`                  | If set to 1, the drone can use walking paths.                                                              |
| `can_fly`                   | If set to 1, the drone can use flying paths.                                                               |
| `never_consider_line_of_sight`| If set to 1, the pathfinding will ignore line of sight checks.                                             |

### GenomeDataComponent

Provides genetic information for creature interactions and AI.

| Attribute         | Description                                                                                                |
| :---------------- | :--------------------------------------------------------------------------------------------------------- |
| `herd_id`         | Identifier for the herd or group the creature belongs to.                                                  |
| `food_chain_rank` | The creature's position in the food chain.                                                                 |
| `is_predator`     | If set to 1, the creature is considered a predator.                                                        |

### CharacterPlatformingComponent

Manages the drone's movement capabilities, particularly for flying.

| Attribute         | Description                                                                                                |
| :---------------- | :--------------------------------------------------------------------------------------------------------- |
| `fly_speed_max_up`| Maximum upward speed when flying.                                                                          |
| `fly_speed_max_down`| Maximum downward speed when flying.                                                                        |
| `fly_speed_mult`  | Multiplier for the drone's base flying speed.                                                              |
| `fly_velocity_x`  | Horizontal velocity when flying.                                                                           |

### HitboxComponent

Defines the collision area of the drone.

| Attribute    | Description                                                                                                |
| :----------- | :--------------------------------------------------------------------------------------------------------- |
| `aabb_min_x` | Minimum X-coordinate of the Axis-Aligned Bounding Box (AABB).                                              |
| `aabb_max_x` | Maximum X-coordinate of the AABB.                                                                          |
| `aabb_min_y` | Minimum Y-coordinate of the AABB.                                                                          |
| `aabb_max_y` | Maximum Y-coordinate of the AABB.                                                                          |

### CharacterDataComponent

Basic character data, including mass.

| Attribute | Description                                                                                                |
| :-------- | :--------------------------------------------------------------------------------------------------------- |
| `mass`    | The mass of the character.                                                                                 |

## Additional Entity

This section defines a specific effect applied to the Healer Drone.

### GameEffectComponent

Applies a game effect to the entity.

| Attribute | Description                                                                                                |
| :-------- | :--------------------------------------------------------------------------------------------------------- |
| `effect`  | The type of game effect to apply (e.g., "PROTECTION_FREEZE").                                              |
| `frames`  | The duration of the effect in frames (-1 for infinite).                                                    |