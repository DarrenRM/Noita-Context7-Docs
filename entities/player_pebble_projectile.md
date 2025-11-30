---
title: Player Pebble Projectile
category: entities
---

# Player Pebble Projectile

This document details the configuration of the "Player Pebble" projectile entity in Noita, focusing on its physics, AI, and damage properties. This entity is designed to behave like a physics-driven projectile with unique movement and interaction capabilities.

## Core Components

### PhysicsAIComponent
Controls the projectile's movement and responsiveness to forces.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the target vector for movement.                           |
| `force_coeff`             | Coefficient for applying force to the projectile.                           |
| `force_balancing_coeff`   | Coefficient for balancing forces applied to the projectile.                 |
| `force_max`               | Maximum force that can be applied to the projectile.                        |
| `torque_coeff`            | Coefficient for applying torque (rotational force).                         |
| `torque_balancing_coeff`  | Coefficient for balancing applied torque.                                   |
| `torque_max`              | Maximum torque that can be applied to the projectile.                       |
| `damage_deactivation_prob`| Probability of deactivation upon taking damage.                             |
| `damage_deactivation_time_min` | Minimum duration before deactivation after taking damage.                |
| `damage_deactivation_time_max` | Maximum duration before deactivation after taking damage.                |

### PhysicsBodyComponent
Defines the physical properties of the projectile's body.

| Attribute               | Description                                      |
| :---------------------- | :----------------------------------------------- |
| `allow_sleep`           | Whether the body can enter a sleep state.        |
| `angular_damping`       | Resistance to rotational movement.               |
| `fixed_rotation`        | Whether the object's rotation is fixed.          |
| `is_bullet`             | If this body is treated as a bullet.             |
| `linear_damping`        | Resistance to linear movement.                   |
| `on_death_leave_physics_body` | If the physics body persists after death. |

### PhysicsImageShapeComponent
Defines the visual shape and collision properties based on an image.

| Attribute    | Description                                     |
| :----------- | :---------------------------------------------- |
| `image_file` | Path to the image file used for the shape.      |
| `centered`   | Whether the image is centered on the entity.    |
| `material`   | The physics material applied to the shape.      |
| `offset_x`   | Horizontal offset of the shape.                 |
| `offset_y`   | Vertical offset of the shape.                   |

## Base Enemy Configuration (`base_enemy_basic.xml`)

This projectile inherits properties from a basic enemy template, which are then modified.

### AnimalAIComponent
Governs the AI behavior of the projectile.

| Attribute                     | Description                                                              |
| :---------------------------- | :----------------------------------------------------------------------- |
| `escape_if_damaged_probability` | Probability to escape when damaged.                                      |
| `food_material`               | Material considered as food.                                             |
| `attack_melee_enabled`        | Whether melee attacks are enabled.                                       |
| `attack_melee_max_distance`   | Maximum distance for melee attacks.                                      |
| `attack_dash_enabled`         | Whether dash attacks are enabled.                                        |
| `attack_dash_distance`        | Distance for dash attacks.                                               |
| `attack_dash_damage`          | Damage dealt by dash attacks.                                            |
| `creature_detection_range_x`  | Horizontal range for detecting creatures.                                |
| `creature_detection_range_y`  | Vertical range for detecting creatures.                                  |
| `needs_food`                  | Whether the entity requires food.                                        |
| `can_fly`                     | Whether the entity can fly.                                              |

### DamageModelComponent
Manages the health and damage-related properties.

| Attribute                     | Description                                                              |
| :---------------------------- | :----------------------------------------------------------------------- |
| `hp`                          | Health points of the entity.                                             |
| `ragdoll_filenames_file`      | File containing ragdoll filenames.                                       |
| `fire_probability_of_ignition`| Probability of igniting from fire.                                       |
| `ragdoll_material`            | Physics material for the ragdoll.                                        |
| `blood_multiplier`            | Multiplier for blood effects.                                            |
| `ragdoll_blood_amount_absolute`| Absolute amount of blood from ragdoll.                                   |
| `blood_material`              | Material of the blood.                                                   |
| `blood_sprite_directional`    | Entity for directional blood splatters.                                  |
| `blood_sprite_large`          | Entity for large blood splatters.                                        |
| `healing_particle_effect_entity`| Entity for healing particle effects.                                     |

#### `damage_multipliers`
Defines multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.0`      |
| `fire`      | `0.0`      |
| `ice`       | `-1`       |

### CharacterPlatformingComponent
Handles character movement and platforming abilities.

| Attribute           | Description                               |
| :------------------ | :---------------------------------------- |
| `jump_velocity_y`   | Vertical velocity for jumping.            |
| `run_velocity`      | Horizontal running speed.                 |
| `fly_speed_max_up`  | Maximum upward flight speed.              |
| `fly_speed_max_down`| Maximum downward flight speed.            |
| `fly_velocity_x`    | Horizontal flight speed.                  |

### HitboxComponent
Defines the bounding box for hit detection.

| Attribute    | Description                               |
| :----------- | :---------------------------------------- |
| `aabb_max_x` | Maximum X-coordinate of the bounding box. |
| `aabb_max_y` | Maximum Y-coordinate of the bounding box. |
| `aabb_min_x` | Minimum X-coordinate of the bounding box. |
| `aabb_min_y` | Minimum Y-coordinate of the bounding box. |

### CharacterDataComponent
General character data, including collision and mass.

| Attribute              | Description                                      |
| :--------------------- | :----------------------------------------------- |
| `collision_aabb_min_x` | Minimum X-coordinate for collision.              |
| `collision_aabb_max_x` | Maximum X-coordinate for collision.              |
| `collision_aabb_min_y` | Minimum Y-coordinate for collision.              |
| `collision_aabb_max_y` | Maximum Y-coordinate for collision.              |
| `mass`                 | Mass of the character.                           |

## Other Key Components

### MaterialInventoryComponent
Manages the materials contained within the entity.

| Attribute               | Description                                      |
| :---------------------- | :----------------------------------------------- |
| `drop_as_item`          | Whether materials drop as items.                 |
| `leak_on_damage_percent`| Percentage of damage at which materials leak.    |

#### `count_per_material_type`
Specifies the quantity of each material.

| Material    | Count |
| :---------- | :---- |
| `blood_cold`| `50`  |

### LightComponent
Adds a light source to the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `radius`  | The radius of the light.                  |
| `offset_y`| Vertical offset of the light source.      |
| `r`       | Red component of the light color.         |
| `g`       | Green component of the light color.       |
| `b`       | Blue component of the light color.        |

### ExplosionComponent
Defines explosion behavior when triggered. Two instances are present: one for `ON_DEATH` and one for `ON_TIMER`.

| Trigger Type | Description