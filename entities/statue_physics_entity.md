---
title: Statue Physics Entity
category: entities
---

# Statue Physics Entity

This document details the `statue_physics.xml` entity, which defines a physics-based enemy in Noita.

## Core Components

This entity utilizes several key components to define its behavior and appearance.

### PhysicsAIComponent

Manages the AI-driven physics interactions of the entity.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `target_vec_max_len`      | Maximum length of the target vector for movement.                           |
| `force_coeff`             | Coefficient for applying force.                                             |
| `force_balancing_coeff`   | Coefficient for balancing forces.                                           |
| `force_max`               | Maximum force that can be applied.                                          |
| `torque_coeff`            | Coefficient for applying torque.                                            |
| `torque_balancing_coeff`  | Coefficient for balancing torque.                                           |
| `torque_max`              | Maximum torque that can be applied.                                         |
| `damage_deactivation_probability` | Probability of deactivating due to damage.                              |
| `damage_deactivation_time_min`    | Minimum time before deactivation after taking damage.                   |
| `damage_deactivation_time_max`    | Maximum time before deactivation after taking damage.                   |

### PhysicsBodyComponent

Defines the physical properties of the entity's body.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `allow_sleep`           | Allows the body to enter a sleep state.         |
| `angular_damping`       | Damping applied to angular velocity.            |
| `fixed_rotation`        | Prevents the body from rotating.                |
| `is_bullet`             | Indicates if the body is a bullet.              |
| `linear_damping`        | Damping applied to linear velocity.             |
| `on_death_leave_physics_body` | Leaves a physics body upon death.           |

### PhysicsImageShapeComponent

Defines the collision shape based on an image.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `image_file`  | Path to the image file used for the shape.      |
| `centered`    | Whether the image is centered.                  |
| `material`    | The physics material of the shape.              |
| `offset_x`    | X-axis offset for the shape.                    |
| `offset_y`    | Y-axis offset for the shape.                    |

### Base Entity (`base_enemy_flying.xml`)

This entity inherits from `base_enemy_flying.xml`, gaining its fundamental AI and combat capabilities.

#### AnimalAIComponent

Controls the creature's AI behavior.

| Attribute                     | Description                                         |
| :---------------------------- | :-------------------------------------------------- |
| `preferred_job`               | The preferred job for the AI.                       |
| `attack_ranged_min_distance`  | Minimum distance for ranged attacks.                |
| `attack_ranged_max_distance`  | Maximum distance for ranged attacks.                |
| `creature_detection_range_x`  | X-axis range for detecting creatures.               |
| `creature_detection_range_y`  | Y-axis range for detecting creatures.               |
| `attack_ranged_action_frame`  | Frame for initiating ranged attacks.                |
| `attack_melee_action_frame`   | Frame for initiating melee attacks.                 |
| `sense_creatures`             | Enables creature sensing.                           |
| `attack_ranged_enabled`       | Enables ranged attacks.                             |
| `attack_melee_enabled`        | Enables melee attacks.                              |
| `can_fly`                     | Allows the creature to fly.                         |
| `eye_offset_y`                | Y-axis offset for the creature's eyes.              |
| `attack_ranged_offset_y`      | Y-axis offset for ranged attacks.                   |

#### DamageModelComponent

Manages the entity's health and damage resistances.

| Attribute                 | Description                                     |
| :------------------------ | :---------------------------------------------- |
| `hp`                      | Hit points of the entity.                       |
| `ragdoll_material`        | Material of the ragdoll upon death.             |
| `blood_material`          | Material of the blood effect.                   |
| `blood_spray_material`    | Material of the blood spray effect.             |
| `fire_probability_of_ignition` | Probability of igniting from fire.            |
| `air_needed`              | Whether the entity needs air to survive.        |
| `physics_objects_damage`  | Whether physics objects deal damage to the entity. |

##### damage_multipliers

Defines multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.5`      |
| `projectile`| `0.5`      |
| `explosion` | `1.2`      |
| `electricity`| `0`        |
| `fire`      | `0`        |

#### SpriteComponent

Defines the visual sprite for the entity.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `image_file` | Path to the sprite image file.                  |
| `offset_x` | X-axis offset for the sprite.                   |
| `offset_y` | Y-axis offset for the sprite.                   |

#### PathFindingGridMarkerComponent

Marks the entity on the pathfinding grid.

| Attribute      | Description                                     |
| :------------- | :---------------------------------------------- |
| `marker_work_flag` | Flag used for pathfinding.                    |

#### PathFindingComponent

Handles pathfinding logic for the entity.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `distance_to_reach_node_x` | X-axis distance to reach a pathfinding node.    |
| `distance_to_reach_node_y` | Y-axis distance to reach a pathfinding node.    |
| `frames_to_get_stuck`   | Frames before considering the entity stuck.     |
| `can_jump`              | Whether the entity can jump.                    |
| `can_fly`               | Whether the entity can fly.                     |
| `jump_speed`            | Speed of the entity's jump.                     |

#### GenomeDataComponent

Contains genetic information for the entity.

| Attribute         | Description                                     |
| :---------------- | :---------------------------------------------- |
| `herd_id`         | Identifier for the entity's herd.               |
| `food_chain_rank` | Rank in the food chain.                         |
| `is_predator`     | Whether the entity is a predator.               |

#### CharacterPlatformingComponent

Manages platforming movement.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `jump_velocity_y` | Y-axis velocity for jumping.                    |
| `run_velocity` | Running speed of the entity.                    |

#### HitboxComponent

Defines the entity's hitbox for interactions.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `aabb_max_x` | Maximum X-axis extent of the hitbox.            |
| `aabb_max_y` | Maximum Y-axis extent of the hitbox.            |
| `aabb_min_x` | Minimum X-axis extent of the hitbox.            |
| `aabb_min_y` | Minimum Y-axis extent of the hitbox.            |

#### CameraBoundComponent

Manages how the entity interacts with the camera.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `max_count` | Maximum number of entities of this type.        |
| `distance`  | Distance from the camera to affect the entity.  |

#### CharacterDataComponent

Stores general character data.

| Attribute         | Description                                     |
| :---------------- | :---------------------------------------------- |
| `collision_aabb_min_x` | Minimum X-axis for collision.                 |
| `collision_aabb_max_x` | Maximum X-axis for collision.                 |
| `collision_aabb_min_y` | Minimum Y-axis for collision.                 |
| `collision_aabb_max_y` | Maximum Y-axis for collision.                 |
| `mass`            | Mass of the entity.                             |

#### SpriteStainsComponent

Manages sprite stains.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `_enabled` | Whether sprite stains are enabled.              |

### SpriteComponent (Emissive)

Defines an emissive sprite for the entity.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `image_file`        | Path to the emissive sprite image file.         |
| `rect_animation`    | Current rectangle animation.                    |
| `next_rect_animation` | Next rectangle animation.                       |
| `special_scale_x`   | Special scaling factor on the X-axis.           |
| `has_special_scale` | Whether special scaling is applied.             |
| `emissive`          | Makes the sprite emissive.                      |
| `additive`          | Uses additive blending for the sprite.          |
| `offset_x`          | X-axis offset for the sprite.                   |
| `offset_y`          | Y-axis offset for the sprite.                   |

### CollisionTriggerComponent

Defines a trigger area for collision events.

| Attribute                   | Description                                     |
| :-------------------------- | :---------------------------------------------- |
| `width`                     | Width of the trigger area.                      |
| `height`                    | Height of the trigger area.                     |
| `radius`                    | Radius of the trigger area.                     |
| `required_tag`              | Tag required for the trigger to activate.       |
| `timer_for_destruction`     | Timer for destruction when triggered.           |
| `destroy_this_entity_when_triggered` | Whether to destroy the entity when triggered. |

### LuaComponent

Allows for custom Lua scripting.

| Attribute                     | Description                                     |
| :---------------------------- | :---------------------------------------------- |
| `script_collision_trigger_hit` | Path to the Lua script executed on trigger hit. |

### AudioComponent

Manages sound effects for the entity.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `file`      | Path to the audio bank file.                    |
| `event_root`| Root event name for the entity's sounds.        |

### AudioLoopComponent

Manages looping sound effects.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `file`      | Path to the audio bank file.                    |
| `event_name`| Name of the looping sound event.                |
| `set_speed_parameter` | Whether to set speed parameter for the loop. |
| `auto_play` | Whether the loop plays automatically.           |

### SpriteParticleEmitterComponent

Emits particles from the entity's sprite.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `sprite_file`           | Path to the particle sprite file.               |
| `delay`                 | Delay before particle emission starts.          |
| `lifetime`              | Lifetime of the particles.                      |
| `sprite_centered`       | Whether the particle sprite is centered.        |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of the particles.               |
| `color_change.r`, `color_change.g`, `color_change.b`, `color_change.a` | Color change over particle lifetime.          |
| `velocity.x`, `velocity.y` | Initial velocity of the particles.            |
| `gravity.x`, `gravity.y` | Gravity applied to the particles.               |
| `velocity_slowdown`     | Slowdown factor for particle velocity.          |
| `rotation`              | Initial rotation of the particles.              |
| `angular_velocity`      | Angular velocity of the particles.              |
| `use_rotation_from_entity` | Whether to use entity's rotation for particles. |
| `use_velocity_as_rotation` | Whether to use particle velocity as rotation.   |
| `scale.x`, `scale.y`    | Initial scale of the particles.                 |
| `scale_velocity.x`, `scale_velocity.y` | Scale change over particle lifetime.          |
| `additive`              | Uses additive blending for particles.           |
| `emissive`              | Makes particles emissive.                       |
| `emission_interval_min_frames` | Minimum frames between particle emissions.    |
| `emission_interval_max_frames` | Maximum frames between particle emissions.    |
| `count_min`             | Minimum number of particles emitted per burst.  |
| `count_max`             | Maximum number of particles emitted per burst.  |

### Inherited Entity

An entity with an `InheritTransformComponent` and `GameEffectComponent`.

#### GameEffectComponent

Applies a game effect to the entity.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of game effect applied.                |
| `frames`  | Duration of the effect in frames (-1 for infinite). |