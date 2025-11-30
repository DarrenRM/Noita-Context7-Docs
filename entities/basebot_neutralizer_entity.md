---
title: Basebot Neutralizer Entity
category: entities
---

# Basebot Neutralizer Entity

This document details the `basebot_neutralizer.xml` entity, which defines the behavior and appearance of the Neutralizer enemy in Noita.

## Core Components

The Neutralizer is a flying robot enemy with ranged attack capabilities and defensive properties.

### AnimalAIComponent

This component governs the AI and combat behavior of the Neutralizer.

| Attribute                     | Value                                     | Description                                                                 |
| :---------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault`                              | Default AI behavior.                                                        |
| `creature_detection_range_x`  | `250`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `250`                                     | Vertical range for detecting creatures.                                     |
| `sense_creatures`             | `1`                                       | Enables creature sensing.                                                   |
| `attack_ranged_enabled`       | `1`                                       | Enables ranged attacks.                                                     |
| `attack_melee_enabled`        | `0`                                       | Disables melee attacks.                                                     |
| `can_fly`                     | `1`                                       | Allows the entity to fly.                                                   |
| `can_walk`                    | `0`                                       | Prevents the entity from walking.                                           |
| `attack_ranged_entity_file`   | `data/entities/projectiles/neutralizershot.xml` | Specifies the projectile entity used for ranged attacks.                    |
| `attack_ranged_max_distance`  | `200`                                     | Maximum distance for ranged attacks.                                        |
| `attack_ranged_frames_between`| `60`                                      | Frames between consecutive ranged attacks.                                  |

### DamageModelComponent

Defines the health and damage resistances of the Neutralizer.

| Attribute             | Value     | Description                                     |
| :-------------------- | :-------- | :---------------------------------------------- |
| `hp`                  | `14.5`    | Hit points of the Neutralizer.                  |
| `ragdoll_filenames_file`| `data/ragdolls/basebot/filenames_neutralizer.txt` | File defining the ragdoll for this entity.      |
| `projectile`          | `0.0`     | Damage multiplier from projectiles (effectively immune). |

### SpriteComponent

Controls the visual representation of the Neutralizer.

| Attribute      | Value                                | Description                                     |
| :------------- | :----------------------------------- | :---------------------------------------------- |
| `image_file`   | `data/enemies_gfx/basebot_neutralizer.xml` | Main sprite graphic file.                       |

### CharacterPlatformingComponent

Manages movement properties, particularly for flying.

| Attribute         | Value | Description                               |
| :---------------- | :---- | :---------------------------------------- |
| `fly_speed_max_up`| `40`  | Maximum upward flight speed.              |
| `fly_speed_max_down`| `40`  | Maximum downward flight speed.            |
| `fly_speed_mult`  | `10`  | Multiplier for flight speed.              |
| `fly_velocity_x`  | `40`  | Horizontal flight speed.                  |

### HitboxComponent

Defines the collision area for the Neutralizer.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-8`  | Minimum X-axis boundary of the hitbox.    |
| `aabb_max_x`| `8`   | Maximum X-axis boundary of the hitbox.    |
| `aabb_min_y`| `-7`  | Minimum Y-axis boundary of the hitbox.    |
| `aabb_max_y`| `8`   | Maximum Y-axis boundary of the hitbox.    |

## Additional Components

### ParticleEmitterComponent

Responsible for visual effects, such as emitting plasma.

| Attribute                 | Value                               | Description                                     |
| :------------------------ | :---------------------------------- | :---------------------------------------------- |
| `emitted_material_name`   | `plasma_fading`                     | The material of the emitted particles.          |
| `y_vel_min`               | `40`                                | Minimum vertical velocity of particles.         |
| `y_vel_max`               | `120`                               | Maximum vertical velocity of particles.         |
| `count_min`               | `1`                                 | Minimum number of particles emitted per burst.  |
| `count_max`               | `1`                                 | Maximum number of particles emitted per burst.  |
| `lifetime_min`            | `0.2`                               | Minimum particle lifetime in seconds.           |
| `lifetime_max`            | `0.7`                               | Maximum particle lifetime in seconds.           |
| `emit_cosmetic_particles` | `1`                                 | Emits cosmetic particles (visual only).         |
| `emission_interval_min_frames` | `1`                               | Minimum frames between emission bursts.         |
| `emission_interval_max_frames` | `3`                                | Maximum frames between emission bursts.         |

### AudioComponent & AudioLoopComponent

Handle sound effects for the Neutralizer.

| Component          | Attribute     | Value                               | Description                                     |
| :----------------- | :------------ | :---------------------------------- | :---------------------------------------------- |
| `AudioComponent`   | `file`        | `data/audio/Desktop/animals.bank`   | Audio bank file.                                |
| `AudioComponent`   | `event_root`  | `animals/drone_lasership`           | Root event for animal sounds.                   |
| `AudioLoopComponent`| `event_name`  | `animals/drone_lasership/movement_loop`| Name of the movement loop sound event.          |
| `AudioLoopComponent`| `auto_play`   | `1`                                 | Sound loop plays automatically.                 |

### GameEffectComponent

Applies passive effects to the Neutralizer.

| Effect              | Frames | Description                                     |
| :------------------ | :----- | :---------------------------------------------- |
| `PROTECTION_FREEZE` | `-1`   | Grants immunity to freezing effects.            |
| `PROTECTION_PROJECTILE`| `-1`   | Grants immunity to projectile damage (redundant with DamageModelComponent). |

### LuaComponent

Integrates custom Lua scripting for advanced behavior.

| Attribute           | Value                                       | Description                                     |
| :------------------ | :------------------------------------------ | :---------------------------------------------- |
| `script_source_file`| `data/scripts/animals/basebot_neutralizer_check.lua` | Path to the Lua script file.                    |
| `execute_every_n_frame`| `40`                                        | How often the script is executed (in frames).   |

### SpriteComponent (Emissive)

Defines the emissive sprite for visual flair.

| Attribute | Value                                     | Description                                     |
| :-------- | :---------------------------------------- | :---------------------------------------------- |
| `image_file`| `data/enemies_gfx/basebot_neutralizer_emissive.xml` | Emissive sprite graphic file.                   |
| `emissive`| `1`                                       | Enables emissive properties.                    |
| `additive`| `1`                                       | Uses additive blending for the emissive effect. |
| `rect_animation`| `walk`                                    | Specifies a rectangle animation for the sprite. |