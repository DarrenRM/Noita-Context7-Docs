---
title: Small Circle Blood Projectile
category: entities
---

# Small Circle Blood Projectile

This document describes the `circle_blood_small.xml` entity, which defines a small, circular blood projectile. It's primarily used for visual effects and particle emission.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles that make up the visual effect of the projectile.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `blood`      | The material of the particles being emitted.                                |
| `create_real_particles`   | `1`          | Indicates that actual particles should be created, not just cosmetic ones. |
| `gravity.y`               | `0.0`        | No vertical gravity applied to the emitted particles.                       |
| `lifetime_min`            | `8`          | Minimum lifetime of emitted particles in frames.                            |
| `lifetime_max`            | `15`         | Maximum lifetime of emitted particles in frames.                            |
| `count_min`               | `1`          | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`          | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`          | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`          | Particles fade out as their lifetime decreases.                             |
| `airflow_force`           | `0.251`      | Force applied by airflow to the particles.                                  |
| `airflow_time`            | `1.01`       | Duration of airflow influence on particles.                                 |
| `airflow_scale`           | `0.05`       | Scale of the airflow effect.                                                |
| `image_animation_file`    | `...circle_256.png` | The sprite sheet used for particle animation.                               |
| `image_animation_speed`   | `1`          | Speed of the particle image animation.                                      |
| `set_magic_creation`      | `1`          | Marks this as a magic-related creation.                                     |
| `is_emitting`             | `1`          | The particle emitter is active.                                             |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `60`  | The entity will exist for 60 frames.      |

## Entity Attributes

| Attribute | Value             | Description                                                                 |
| :-------- | :---------------- | :-------------------------------------------------------------------------- |
| `name`    | `$projectile_default` | A placeholder name, likely overridden by specific projectile definitions. |
| `tags`    | `projectile_player` | Indicates this entity is a projectile fired by the player.                  |