---
title: Circle Blood Projectile
category: entities
---

# Circle Blood Projectile

This entity defines a projectile that emits blood particles. It's designed to be a simple, player-created projectile with a specific particle effect.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `blood`      | The material of the particles to be emitted.                                |
| `create_real_particles`   | `1`          | Whether to create actual game particles (as opposed to cosmetic ones).      |
| `gravity.y`               | `0.0`        | The gravitational pull on the emitted particles along the Y-axis.           |
| `lifetime_min`            | `8`          | Minimum lifetime of emitted particles in frames.                            |
| `lifetime_max`            | `15`         | Maximum lifetime of emitted particles in frames.                            |
| `count_min`               | `1`          | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`          | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`          | Whether the particles should be rendered on the game grid.                  |
| `fade_based_on_lifetime`  | `1`          | Whether particles should fade out as their lifetime decreases.              |
| `airflow_force`           | `0.251`      | The force applied to particles by airflow.                                  |
| `airflow_time`            | `1.01`       | The duration for which airflow affects particles.                           |
| `airflow_scale`           | `0.05`       | The scaling factor for airflow effects.                                     |
| `image_animation_file`    | `data/particles/image_emitters/circle_256.png` | The image file used for particle animation.                               |
| `image_animation_speed`   | `1`          | The speed of the particle image animation.                                  |
| `set_magic_creation`      | `1`          | Marks the particles as being magically created.                             |
| `is_emitting`             | `1`          | Enables particle emission.                                                  |

### LifetimeComponent

This component defines the lifetime of the projectile itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `260` | The total lifetime of the projectile in frames. |