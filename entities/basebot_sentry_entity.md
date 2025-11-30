---
title: Basebot Sentry Entity
category: entities
---

# Basebot Sentry Entity

This document details the configuration of the `basebot_sentry.xml` entity, a flying robotic enemy in Noita.

## Core Components

The Sentry is built upon a `Base file="data/entities/base_enemy_robot.xml"`, inheriting its fundamental robot properties.

### AnimalAIComponent

This component governs the Sentry's behavior and combat capabilities.

| Attribute                     | Value                                  | Description                                                                 |
| :---------------------------- | :------------------------------------- | :-------------------------------------------------------------------------- |
| `creature_detection_range_x`  | `250`                                  | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `250`                                  | Vertical range for detecting creatures.                                     |
| `sense_creatures`             | `1`                                    | Enables creature sensing.                                                   |
| `attack_ranged_enabled`       | `1`                                    | Enables ranged attacks.                                                     |
| `attack_melee_enabled`        | `0`                                    | Disables melee attacks.                                                     |
| `can_fly`                     | `1`                                    | Allows the entity to fly.                                                   |
| `can_walk`                    | `0`                                    | Prevents the entity from walking.                                           |
| `attack_ranged_entity_file`   | `data/entities/projectiles/sentryshot.xml` | Specifies the projectile entity used for ranged attacks.                    |
| `attack_ranged_max_distance`  | `200`                                  | Maximum distance for ranged attacks.                                        |
| `attack_ranged_frames_between`| `60`                                   | Frames to wait between ranged attacks.                                      |
| `attack_ranged_action_frame`  | `3`                                    | Frame within the attack animation to fire the projectile.                   |

### DamageModelComponent

Defines the Sentry's health and damage resistances.

| Attribute        | Value    | Description                                     |
| :--------------- | :------- | :---------------------------------------------- |
| `hp`             | `14.5`   | Hit points of the Sentry.                       |
| `projectile`     | `0.0`    | Damage multiplier from projectiles (effectively immune). |

### SpriteComponent

Controls the visual appearance of the Sentry.

| Attribute     | Value                               | Description                                     |
| :------------ | :---------------------------------- | :---------------------------------------------- |
| `image_file`  | `data/enemies_gfx/basebot_sentry.xml` | Path to the primary sprite definition.          |

### PathFindingComponent

Configures the entity's movement capabilities.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `can_fly` | `1`   | Enables flight pathfinding.                     |
| `can_walk`| `0`   | Disables walking pathfinding.                   |

### CharacterPlatformingComponent

Manages movement parameters, particularly for flight.

| Attribute         | Value | Description                                     |
| :---------------- | :---- | :---------------------------------------------- |
| `fly_speed_max_up`| `40`  | Maximum upward flight speed.                    |
| `fly_speed_max_down`| `40`  | Maximum downward flight speed.                  |
| `fly_speed_mult`  | `10`  | Multiplier for flight speed.                    |
| `fly_velocity_x`  | `40`  | Horizontal flight speed.                        |

### HitboxComponent

Defines the collision area for the Sentry.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `aabb_min_x`| `-8`  | Minimum X-axis coordinate of the bounding box.  |
| `aabb_max_x`| `8`   | Maximum X-axis coordinate of the bounding box.  |
| `aabb_min_y`| `-7`  | Minimum Y-axis coordinate of the bounding box.  |
| `aabb_max_y`| `8`   | Maximum Y-axis coordinate of the bounding box.  |

## Visual and Audio Elements

### ParticleEmitterComponent

Generates visual effects, specifically blue sparks.

| Attribute                   | Value   | Description                                     |
| :-------------------------- | :------ | :---------------------------------------------- |
| `emitted_material_name`     | `spark_blue` | The material of the emitted particles.          |
| `y_vel_min`                 | `40`    | Minimum vertical velocity of sparks.            |
| `y_vel_max`                 | `120`   | Maximum vertical velocity of sparks.            |
| `count_min`                 | `1`     | Minimum number of sparks emitted per burst.     |
| `count_max`                 | `1`     | Maximum number of sparks emitted per burst.     |
| `lifetime_min`              | `0.2`   | Minimum lifetime of sparks in seconds.          |
| `lifetime_max`              | `0.7`   | Maximum lifetime of sparks in seconds.          |
| `emission_interval_min_frames`| `1`     | Minimum frames between emission bursts.         |
| `emission_interval_max_frames`| `3`     | Maximum frames between emission bursts.         |
| `is_emitting`               | `1`     | Enables particle emission.                      |

### AudioComponent & AudioLoopComponent

Manages the Sentry's sound effects.

| Component           | Attribute     | Value                                | Description                                     |
| :------------------ | :------------ | :----------------------------------- | :---------------------------------------------- |
| `AudioComponent`    | `file`        | `data/audio/Desktop/animals.bank`    | Path to the audio bank.                         |
|                     | `event_root`  | `animals/drone_lasership`            | Root event name for the Sentry's sounds.        |
| `AudioLoopComponent`| `file`        | `data/audio/Desktop/animals.bank`    | Path to the audio bank.                         |
|                     | `event_name`  | `animals/drone_lasership/movement_loop`| Name of the movement loop sound event.          |
|                     | `auto_play`   | `1`                                  | Automatically plays the sound on entity spawn.  |

## Special Properties

### GameEffectComponent

Applies passive effects to the Sentry.

| Effect              | Frames | Description                                     |
| :------------------ | :----- | :---------------------------------------------- |
| `PROTECTION_FREEZE` | `-1`   | Grants immunity to freezing effects.            |
| `PROTECTION_PROJECTILE`| `-1`   | Grants immunity to projectile damage.           |

### LuaComponent

Integrates custom Lua scripting for advanced behavior.

| Attribute          | Value                                       | Description                                     |
| :----------------- | :------------------------------------------ | :---------------------------------------------- |
| `script_source_file`| `data/scripts/animals/basebot_sentry_check.lua` | Path to the Lua script file.                    |
| `execute_every_n_frame`| `40`                                        | How often the script is executed (in frames).   |