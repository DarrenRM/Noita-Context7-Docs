---
title: Tiny Spark (Red) Particle Emitter
category: entities
---

# Tiny Spark (Red) Particle Emitter

This document describes the configuration for a particle emitter that generates "tiny red sparks" in Noita. It utilizes two primary components: `SpriteParticleEmitterComponent` for visual sprite emission and `ParticleEmitterComponent` for material-based particle emission.

## SpriteParticleEmitterComponent

This component defines the visual appearance and behavior of the sprites used for the sparks.

### Key Attributes:

| Attribute                 | Description                                                                 | Value Example      |
| :------------------------ | :-------------------------------------------------------------------------- | :----------------- |
| `sprite_file`             | Path to the XML file defining the sprite's appearance.                      | `data/particles/tinyspark_02.xml` |
| `lifetime`                | Duration the sprite particle exists (0 means it's managed by the other emitter). | `0`                |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of the sprite particle (RGBA).                                | `1, 1, 1, 1` (White) |
| `scale.x`, `scale.y`      | Initial scale of the sprite particle.                                       | `1, 1`             |
| `scale_velocity.x`, `scale_velocity.y` | Rate at which the sprite particle scales over its lifetime.                 | `-0.1, -0.1` (Shrinks) |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls the timing between sprite emissions.                               | `2, 3`             |
| `count_min`, `count_max`  | Number of sprite particles emitted per emission event.                      | `1, 1`             |
| `randomize_rotation.min`, `randomize_rotation.max` | Random range for initial sprite rotation.                                   | `-3.1415, 3.1415` (Full circle) |
| `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y` | Random offset from the emitter's origin for sprite particles.               | `-2` to `2`        |
| `gravity.y`               | Downward acceleration applied to the sprite particles.                      | `10`               |

## ParticleEmitterComponent

This component defines the material-based particles that are emitted, which are often the functional "sparks" that interact with the game world.

### Key Attributes:

| Attribute                 | Description                                                                 | Value Example      |
| :------------------------ | :-------------------------------------------------------------------------- | :----------------- |
| `emitted_material_name`   | The name of the material to be emitted as particles.                        | `spark_red`        |
| `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max` | Random offset from the emitter's origin for particle emission.              | `-1` to `1`        |
| `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max` | Random range for the initial velocity of emitted particles.                 | `-2` to `2`        |
| `count_min`, `count_max`  | Number of particles emitted per emission event.                             | `1, 3`             |
| `is_trail`                | Whether the particles should leave a trail.                                 | `1` (Yes)          |
| `trail_gap`               | Spacing between trail segments.                                             | `1`                |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases.                     | `1` (Yes)          |
| `lifetime_min`, `lifetime_max` | Minimum and maximum duration the particles exist.                           | `0.8, 2.0`         |
| `airflow_force`, `airflow_time`, `airflow_scale` | Parameters controlling how airflow affects the particles.                 | `1.5, 0.401, 0.05` |
| `create_real_particles`   | Whether to create actual game entities for these particles.                 | `0` (No)           |
| `emit_cosmetic_particles` | Whether to emit particles that are purely visual.                           | `1` (Yes)          |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls the timing between particle emissions.                             | `1, 2`             |
| `is_emitting`             | Whether the emitter is currently active.                                    | `1` (Yes)          |