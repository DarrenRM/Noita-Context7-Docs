---
title: Circle Acid Projectile
category: entities
---

# Circle Acid Projectile

This document details the configuration for a player-created acid projectile in Noita, designed for AI-assisted modding.

## Key Components

### ParticleEmitterComponent

This component defines the visual and physical properties of the acid particles emitted by the projectile.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `acid`       | The material of the particles being emitted.                                |
| `create_real_particles`   | `1`          | Indicates that these are actual game particles, not just cosmetic effects.  |
| `gravity.y`               | `0.0`        | No vertical gravity applied to the emitted particles.                       |
| `lifetime_min`            | `8`          | Minimum lifetime of each emitted particle in frames.                        |
| `lifetime_max`            | `15`         | Maximum lifetime of each emitted particle in frames.                        |
| `count_min`               | `1`          | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`          | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`          | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`          | Particles fade out as their lifetime decreases.                             |
| `airflow_force`           | `0.251`      | The force applied by airflow to the particles.                              |
| `airflow_time`            | `1.01`       | The duration airflow affects the particles.                                 |
| `airflow_scale`           | `0.05`       | The scaling factor for airflow effects.                                     |
| `emission_interval_min_frames` | `1`      | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1`      | Maximum frames between particle emissions.                                  |
| `image_animation_file`    | `circle_256.png` | The sprite sheet used for particle animation.                               |
| `image_animation_speed`   | `1`          | Speed of the particle animation.                                            |
| `image_animation_loop`    | `0`          | Particle animation does not loop.                                           |
| `image_animation_raytrace_from_center` | `1` | Raytracing for animation starts from the center of the particle.            |
| `set_magic_creation`      | `1`          | Marks this as a magic-created entity.                                       |
| `is_emitting`             | `1`          | The particle emitter is active.                                             |

### LifetimeComponent

This component defines the total lifetime of the projectile itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `260` | The projectile exists for 260 frames.     |

### AudioComponent

This component handles the sound effects associated with the projectile.

| Attribute   | Value                 | Description                                     |
| :---------- | :-------------------- | :---------------------------------------------- |
| `file`      | `projectiles.bank`    | The audio bank containing projectile sounds.    |
| `event_root`| `player_projectiles/circle_of` | The root event for player projectile sounds. |