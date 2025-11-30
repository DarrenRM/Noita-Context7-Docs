---
title: Circle of Oil Projectile
category: entities
---

# Circle of Oil Projectile

This document describes the `circle_oil.xml` entity, which defines a projectile that emits oil particles.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles that form the "oil" effect.

| Attribute                 | Value                                      | Description                                                                 |
| :------------------------ | :----------------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `oil`                                      | The material of the particles being emitted.                                |
| `create_real_particles`   | `1`                                        | Indicates that actual particles should be created.                          |
| `gravity.y`               | `0.0`                                      | No vertical gravity applied to the emitted particles.                       |
| `lifetime_min`            | `8`                                        | Minimum lifetime of emitted particles in frames.                            |
| `lifetime_max`            | `15`                                       | Maximum lifetime of emitted particles in frames.                            |
| `count_min`               | `1`                                        | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`                                        | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`                                        | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`                                        | Particles fade out as their lifetime decreases.                             |
| `airflow_force`           | `0.251`                                    | The force applied by airflow to the particles.                              |
| `airflow_scale`           | `0.05`                                     | The scaling factor for airflow effects.                                     |
| `image_animation_file`    | `data/particles/image_emitters/circle_256.png` | The image file used for animating the emitted particles.                    |
| `image_animation_speed`   | `1`                                        | The speed of the particle image animation.                                  |
| `image_animation_loop`    | `0`                                        | The particle image animation does not loop.                                 |
| `image_animation_raytrace_from_center` | `1`                                        | Raytracing for animation starts from the center of the image.               |
| `set_magic_creation`      | `1`                                        | Marks this as a magic creation, potentially affecting game mechanics.       |
| `is_emitting`             | `1`                                        | The particle emitter is active.                                             |

### LifetimeComponent

This component defines the total lifetime of the projectile itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `260` | The projectile exists for 260 frames.     |

### AudioComponent

This component handles the sound effects associated with the projectile.

| Attribute   | Value                               | Description                                       |
| :---------- | :---------------------------------- | :------------------------------------------------ |
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank file containing projectile sounds. |
| `event_root`| `player_projectiles/circle_of`      | The root event name for player projectile sounds. |