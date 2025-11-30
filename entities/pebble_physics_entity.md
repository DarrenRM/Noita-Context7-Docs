---
title: Pebble Physics Entity
category: entities
---

# Pebble Physics Entity

This document details the configuration of the "Pebble" entity, focusing on its physics, AI, and combat-related attributes.

## Core Components

### PhysicsAIComponent

Controls the movement and physics-driven behavior of the pebble.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the target vector for movement.                        |
| `force_coeff`             | Coefficient for applying force to movement.                              |
| `force_balancing_coeff`   | Coefficient for balancing forces during movement.                        |
| `force_max`               | Maximum force that can be applied.                                       |
| `torque_coeff`            | Coefficient for applying torque (rotational force).                      |
| `torque_balancing_coeff`  | Coefficient for balancing torque.                                        |
| `torque_max`              | Maximum torque that can be applied.                                      |
| `damage_deactivation_probability` | Probability (in percent) of deactivating due to damage.              |
| `damage_deactivation_time_min`  | Minimum duration (in frames) before deactivation after taking damage. |
| `damage_deactivation_time_max`  | Maximum duration (in frames) before deactivation after taking damage. |

### PhysicsBodyComponent

Defines the physical properties of the pebble's body.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `allow_sleep`             | Whether the physics body can enter a sleep state to save resources.      |
| `angular_damping`         | Damping applied to rotational velocity.                                  |
| `fixed_rotation`          | Whether the object's rotation is fixed.                                  |
| `is_bullet`               | Whether the object is treated as a bullet (e.g., for collision detection). |
| `linear_damping`          | Damping applied to linear velocity.                                      |
| `on_death_leave_physics_body` | Whether the physics body remains after the entity dies.                  |

### PhysicsImageShapeComponent

Defines the shape of the physics body based on an image.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `image_file`  | Path to the image file used for the shape.                               |
| `centered`    | Whether the image is centered on the entity's origin.                    |
| `material`    | The physics material assigned to this shape.                             |
| `offset_x`    | X-axis offset for the image shape.                                       |
| `offset_y`    | Y-axis offset for the image shape.                                       |

## Base Enemy Configuration

The pebble inherits many properties from `base_enemy_basic.xml`.

### AnimalAIComponent

Governs the creature's AI behaviors.

| Attribute                       | Description                                                              |
| :------------------------------ | :----------------------------------------------------------------------- |
| `escape_if_damaged_probability` | Probability (in percent) of escaping when damaged.                       |
| `food_material`                 | The material the creature considers food.                                |
| `attack_melee_enabled`          | Whether melee attacks are enabled.                                       |
| `attack_melee_max_distance`     | Maximum distance for melee attacks.                                      |
| `attack_dash_enabled`           | Whether dash attacks are enabled.                                        |
| `attack_dash_distance`          | Distance of the dash attack.                                             |
| `attack_dash_damage`            | Damage dealt by the dash attack.                                         |
| `creature_detection_range_x`    | X-axis range for detecting creatures.                                    |
| `creature_detection_range_y`    | Y-axis range for detecting creatures.                                    |
| `can_fly`                       | Whether the creature can fly.                                            |
| `needs_food`                    | Whether the creature requires food.                                      |

### DamageModelComponent

Manages health, damage resistances, and death effects.

| Attribute                       | Description                                                              |
| :------------------------------ | :----------------------------------------------------------------------- |
| `hp`                            | Hit points of the entity.                                                |
| `ragdoll_filenames_file`        | Path to a file listing ragdoll sprite filenames.                         |
| `fire_probability_of_ignition`  | Probability (in percent) of igniting from fire damage.                   |
| `ragdoll_material`              | Physics material for the ragdoll.                                        |
| `blood_multiplier`              | Multiplier for blood effects.                                            |
| `ragdoll_blood_amount_absolute` | Absolute amount of blood to spawn from ragdoll.                          |
| `blood_material`                | Physics material for blood.                                              |
| `blood_spray_material`          | Physics material for blood spray.                                        |
| `blood_sprite_directional`      | Path to directional blood splatter particle effect.                     |
| `blood_sprite_large`            | Path to large blood splatter particle effect.                            |
| `healing_particle_effect_entity`| Path to the entity for healing particle effects.                         |

#### Damage Multipliers

Specific multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.0`      |
| `fire`      | `0.0`      |
| `ice`       | `-1`       |

### SpriteComponent

Defines the visual sprite for the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `image_file` | Path to the sprite image file.            |
| `offset_x` | X-axis offset for the sprite.             |
| `offset_y` | Y-axis offset for the sprite.             |

### PathFindingGridMarkerComponent

Marks the entity on the pathfinding grid.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `marker_work_flag` | A flag indicating the type of work this marker represents on the grid. |

### PathFindingComponent

Enables pathfinding capabilities for the entity.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `frames_to_get_stuck` | Number of frames before the entity is considered stuck.                  |
| `can_jump`        | Whether the entity can jump.                                             |
| `can_fly`         | Whether the entity can fly.                                              |

### GenomeDataComponent

Stores genetic information for the creature.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `herd_id`       | Identifier for the creature's herd.                                      |
| `food_chain_rank` | Rank in the food chain.                                                  |
| `is_predator`   | Whether the creature is a predator.                                      |

### CharacterPlatformingComponent

Defines movement parameters for platforming characters.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `jump_velocity_y`   | Vertical velocity applied when jumping.                                  |
| `run_velocity`      | Horizontal running speed.                                                |
| `fly_speed_max_up`  | Maximum upward flying speed.                                             |
| `fly_speed_max_down`| Maximum downward flying speed.                                           |
| `fly_velocity_x`    | Horizontal flying speed.                                                 |

### CameraBoundComponent

Manages the entity's behavior relative to the camera.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `max_count` | Maximum number of entities of this type that can be active.              |
| `distance`  | Distance from the camera that affects entity behavior or activation.     |

### HitboxComponent

Defines the collision hitbox for the entity.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `aabb_max_x`| Maximum X-coordinate of the Axis-Aligned Bounding Box (AABB).            |
| `aabb_max_y`| Maximum Y-coordinate of the AABB.                                        |
| `aabb_min_x`| Minimum X-coordinate of the AABB.                                        |
| `aabb_min_y`| Minimum Y-coordinate of the AABB.                                        |

### ItemChestComponent

Defines loot drop behavior.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `enemy_drop`    | Whether this entity drops items as loot.                                 |
| `item_count_min`| Minimum number of items to drop.                                         |
| `item_count_max`| Maximum number of items to drop.                                         |

### CharacterDataComponent

General character data, including collision bounds and mass.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `collision_aabb_min_x`| Minimum X-coordinate for collision AABB.                                 |
| `collision_aabb_max_x`| Maximum X-coordinate for collision AABB.                                 |
| `collision_aabb_min_y`| Minimum Y-coordinate for collision AABB.                                 |
| `collision_aabb_max_y`| Maximum Y-coordinate for collision AABB.                                 |
| `mass`                | The mass of the character.                                               |

## Other Components

### MaterialInventoryComponent

Manages the materials contained within the entity.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `drop_as_item`          | Whether materials are dropped as items upon death.                       |
| `leak_on_damage_percent`| Percentage of damage that causes materials to leak.                      |

#### Material Counts

| Material    | Count |
| :---------- | :---- |
| `blood_cold`| `50`  |

### ExplosionComponent

Defines explosion effects triggered by various events.

**Trigger: ON_DEATH**
*   `damage`: `2.5`
*   `camera_shake`: `8`
*   `explosion_radius`: `14`
*   `explosion_sprite`: `data/particles/explosion_025_fuel.xml`
*   `load_this_entity`: `data/entities/particles/particle_explosion/main_bluesmoke_small.xml`
*   `create_cell_probability`: `20`
*   `create_cell_material`: `blood_cold`
*   `physics_explosion_power.min`: `1.0`
*   `physics_explosion_power.max`: `1.6`
*   `sparks_count_min`: `7`
*   `sparks_count_max`: `14`
*   `ray_energy`: `200000`

**Trigger: ON_TIMER**
*   `timeout_frames`: `400`
*   `damage`: `2.5`
*   `camera_shake`: `8`
*   `explosion_radius`: `14`
*   `explosion_sprite`: `data/particles/explosion_025_fuel.xml`
*   `load_this_entity`: `data/entities/particles/particle_explosion/main_bluesmoke.xml`
*   `create_cell_probability`: `20`
*   `create_cell_material`: `blood_cold`
*   `physics_explosion_power.min`: `1.0`
*   `physics_explosion_power.max`: `1.6`
*   `sparks_count_min`: `7`
*   `sparks_count_max`: `14`
*   `ray_energy`: `200000`

### CollisionTriggerComponent

Triggers an event when colliding with entities that meet specific criteria.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `width`               | Width of the trigger area.                                               |
| `height`              | Height of the trigger area.                                              |
| `radius`              | Radius of the trigger area.                                              |
| `required_tag`        | Tag of entities required for the trigger to activate.                    |
| `timer_for_destruction`| Timer (in frames) before destruction after trigger activation.           |

### VariableStorageComponent

Stores entity-specific variables.

*   `_tags`: `no_gold_drop` (Indicates no gold drops from this entity).

### AudioLoopComponent

Manages looping audio effects.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | Path to the audio bank file.                                             |
| `event_name`| Name of the audio event to play.                                         |
| `set_speed_parameter` | Whether to set a speed parameter for the audio.                      |
| `auto_play` | Whether the audio should play automatically.                             |

### Entity (Inherited)

This section describes an inherited entity that provides a `GameEffectComponent`.

#### GameEffectComponent

Applies a game effect to the entity.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `effect`  | The type of game effect to apply (e.g., `PROTECTION_MELEE`).             |
| `frames`  | Duration of the effect in frames (-1 for infinite).                      |