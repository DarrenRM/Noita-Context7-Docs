---
title: Circle Fire Projectile
category: entities
---

# Circle Fire Projectile

This document describes the `circle_fire.xml` entity, which defines a player projectile that emits fire particles.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles that create the visual effect of the fire projectile.

| Attribute                 | Value                                    | Description                                                                 |
| :------------------------ | :--------------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `fire`                                   | The material of the particles being emitted.                                |
| `create_real_particles`   | `1`                                      | Whether to create actual game particles (as opposed to cosmetic ones).      |
| `gravity.y`               | `0.0`                                    | The gravitational pull on the emitted particles (0 means no gravity).       |
| `lifetime_min`            | `8`                                      | Minimum lifetime of emitted particles in frames.                            |
| `lifetime_max`            | `15`                                     | Maximum lifetime of emitted particles in frames.                            |
| `count_min`               | `1`                                      | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`                                      | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`                                      | Whether the particles should be rendered on the game grid.                  |
| `fade_based_on_lifetime`  | `1`                                      | Whether particles fade out as their lifetime decreases.                     |
| `airflow_force`           | `0.251`                                  | The force applied by airflow to the particles.                              |
| `airflow_time`            | `1.01`                                   | The duration airflow affects the particles.                                 |
| `airflow_scale`           | `0.05`                                   | The scaling factor for airflow effects.                                     |
| `image_animation_file`    | `data/particles/image_emitters/circle_256.png` | The image file used for particle animation.                                 |
| `image_animation_speed`   | `1`                                      | The speed of the particle image animation.                                  |
| `image_animation_raytrace_from_center` | `1`                                      | Whether the animation rays trace from the center of the image.              |
| `set_magic_creation`      | `1`                                      | Marks this as a magic creation, potentially affecting game mechanics.       |
| `is_emitting`             | `1`                                      | Whether the particle emitter is currently active.                           |

### LifetimeComponent

This component defines the total lifetime of the projectile itself.

| Attribute | Value   | Description                               |
| :-------- | :------ | :---------------------------------------- |
| `lifetime`| `260`   | The total lifetime of the projectile in frames. |

### AudioComponent

This component handles the sound effects associated with the projectile.

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank file containing the sound events. |
| `event_root`| `player_projectiles/circle_of`      | The root event name for player projectile sounds. |