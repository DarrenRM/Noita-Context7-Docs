---
title: Basebot Soldier Entity
category: entities
---

# Basebot Soldier Entity

This document details the configuration for the `basebot_soldier` entity in Noita, focusing on its AI, combat, and visual properties.

## Core Components

The `basebot_soldier` entity inherits from `base_enemy_robot.xml` and extends it with specific attributes.

### AnimalAIComponent

This component governs the soldier's behavior and combat capabilities.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault`                        | Default job assigned to the AI.                                             |
| `creature_detection_range_x`  | `250`                               | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `250`                               | Vertical range for detecting creatures.                                     |
| `needs_food`                  | `0`                                 | Indicates if the entity requires food (0 for no).                           |
| `sense_creatures`             | `1`                                 | Enables creature sensing.                                                   |
| `attack_ranged_enabled`       | `1`                                 | Enables ranged attacks.                                                     |
| `attack_melee_enabled`        | `0`                                 | Disables melee attacks.                                                     |
| `can_fly`                     | `1`                                 | Allows the entity to fly.                                                   |
| `can_walk`                    | `0`                                 | Disables walking.                                                           |
| `attack_ranged_entity_file`   | `data/entities/projectiles/soldiershot.xml` | Specifies the projectile entity used for ranged attacks.                    |
| `attack_ranged_max_distance`  | `200`                               | Maximum distance for ranged attacks.                                        |
| `attack_ranged_frames_between`| `40`                                | Frames to wait between ranged attacks.                                      |
| `attack_ranged_action_frame`  | `3`                                 | Frame within the attack animation where the projectile is fired.            |

### DamageModelComponent

Defines the entity's health and damage resistances.

| Attribute             | Value                               | Description                                                                 |
| :-------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                  | `20.5`                              | Hit points of the entity.                                                   |
| `ragdoll_filenames_file`| `data/ragdolls/basebot/filenames_soldier.txt` | File defining the ragdoll configuration for this entity.                    |
| `damage_multipliers`  |                                     | Modifiers for incoming damage types.                                        |
| `projectile`          | `0.0`                               | Multiplier for projectile damage (0.0 means immune).                        |
| `explosion`           | `0.0`                               | Multiplier for explosion damage (0.0 means immune).                         |

### SpriteComponent

Determines the visual appearance of the entity.

| Attribute      | Value                               | Description                                                                 |
| :------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`   | `data/enemies_gfx/basebot_soldier.xml` | Path to the sprite sheet or definition file.                                |
| `offset_x`     | `0`                                 | Horizontal offset for the sprite.                                           |
| `offset_y`     | `0`                                 | Vertical offset for the sprite.                                             |

### CharacterPlatformingComponent

Controls movement and physics properties.

| Attribute           | Value | Description                                                                 |
| :------------------ | :---- | :-------------------------------------------------------------------------- |
| `run_velocity`      | `20`  | Base horizontal movement speed.                                             |
| `fly_speed_max_up`  | `40`  | Maximum upward flight speed.                                                |
| `fly_speed_max_down`| `40`  | Maximum downward flight speed.                                              |
| `fly_speed_mult`    | `10`  | Multiplier for flight speed.                                                |
| `fly_velocity_x`    | `40`  | Horizontal flight speed.                                                    |

### HitboxComponent

Defines the collision area for the entity.

| Attribute     | Value | Description                                                                 |
| :------------ | :---- | :-------------------------------------------------------------------------- |
| `aabb_min_x`  | `-8`  | Minimum X-coordinate of the Axis-Aligned Bounding Box.                      |
| `aabb_max_x`  | `8`   | Maximum X-coordinate of the Axis-Aligned Bounding Box.                      |
| `aabb_min_y`  | `-7`  | Minimum Y-coordinate of the Axis-Aligned Bounding Box.                      |
| `aabb_max_y`  | `8`   | Maximum Y-coordinate of the Axis-Aligned Bounding Box.                      |

## Visual and Effect Components

### Emissive Sprite Component

This component adds an emissive glow to the soldier, making it stand out.

| Attribute      | Value                                     | Description                                                                 |
| :------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`   | `data/enemies_gfx/basebot_soldier_emissive.xml` | Path to the emissive sprite definition file.                                |
| `emissive`     | `1`                                       | Enables emissive properties.                                                |
| `additive`     | `1`                                       | Uses additive blending for the emissive effect.                             |
| `rect_animation`| `walk`                                    | Specifies the animation to use for the sprite.                              |

### ParticleEmitterComponent

Generates visual effects, such as sparks.

| Attribute                   | Value | Description                                                                 |
| :-------------------------- | :---- | :-------------------------------------------------------------------------- |
| `emitted_material_name`     | `spark_green` | The material of the particles to emit.                                      |
| `y_vel_min`                 | `40`  | Minimum vertical velocity of emitted particles.                             |
| `y_vel_max`                 | `120` | Maximum vertical velocity of emitted particles.                             |
| `count_min`                 | `1`   | Minimum number of particles emitted per emission.                           |
| `count_max`                 | `1`   | Maximum number of particles emitted per emission.                           |
| `lifetime_min`              | `0.2` | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`              | `0.7` | Maximum lifetime of emitted particles in seconds.                           |
| `emission_interval_min_frames`| `1`   | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames`| `3`   | Maximum frames between particle emissions.                                  |
| `is_emitting`               | `1`   | Enables particle emission.                                                  |

### GameEffectComponent

Applies status effects to the entity. The soldier has protections against freeze, explosion, and projectiles.

| Attribute | Value   | Description                                                                 |
| :-------- | :------ | :-------------------------------------------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | Grants immunity to freezing.                                                |
| `effect`  | `PROTECTION_EXPLOSION`| Grants immunity to explosion damage.                                        |
| `effect`  | `PROTECTION_PROJECTILE`| Grants immunity to projectile damage.                                       |
| `frames`  | `-1`    | Indicates the effect is permanent.                                          |

## Audio Components

### AudioComponent

Plays sound effects for the entity.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`   | Path to the audio bank.                                                     |
| `event_root`| `animals/drone_lasership`           | The root event name for sounds associated with this entity.                 |

### AudioLoopComponent

Manages looping sound effects.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`   | Path to the audio bank.                                                     |
| `event_name`| `animals/drone_lasership/movement_loop` | The name of the looping movement sound event.                               |
| `auto_play` | `1`                                 | Starts the sound automatically when the entity is spawned.                  |