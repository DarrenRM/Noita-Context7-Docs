---
title: Player Disappear Effect (Right) Particle Emitter
category: entities
---

# Player Disappear Effect (Right) Particle Emitter

This entity defines a particle emitter responsible for the visual effect of the player disappearing to the right. It utilizes an image animation to create a dissolving or fading appearance.

## Key Components

### ParticleEmitterComponent

This component manages the emission of particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles being emitted (e.g., "spark_player").         |
| `gravity.y`               | Vertical gravity applied to particles (0.0 means no gravity).               |
| `lifetime_min`            | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | Maximum lifetime of emitted particles in seconds.                           |
| `count_min`               | Minimum number of particles emitted per emission.                           |
| `count_max`               | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | Whether particles should be rendered on the game grid.                      |
| `fade_based_on_lifetime`  | If 1, particles fade out as their lifetime decreases.                       |
| `area_circle_radius.min`  | Minimum radius of the emission area (0 means point emission).               |
| `area_circle_radius.max`  | Maximum radius of the emission area (0 means point emission).               |
| `airflow_force`           | Force applied by airflow to particles.                                      |
| `airflow_time`            | Duration of airflow effect on particles.                                    |
| `airflow_scale`           | Scale of the airflow effect.                                                |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                                |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                                |
| `emit_cosmetic_particles` | If 1, emits cosmetic particles (visual effects not affecting gameplay).     |
| `image_animation_file`    | Path to the image file used for particle animation.                         |
| `image_animation_speed`   | Speed of the image animation (frames per second).                           |
| `image_animation_loop`    | If 1, the image animation will loop.                                        |
| `offset.x`                | Horizontal offset of the emitter's origin.                                  |
| `offset.y`                | Vertical offset of the emitter's origin.                                    |
| `is_emitting`             | If 1, the emitter is active and will emit particles.                        |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of the entity in seconds. |