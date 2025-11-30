---
title: Transmutation Effect Particle Emitter
category: entities/particles
---

# Transmutation Effect Particle Emitter

This entity defines a particle effect used for transmutations, likely in a shop or similar context. It utilizes an image animation for its visual appearance and emits purple sparks.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles being emitted (e.g., `spark_purple_bright`). |
| `gravity.y`               | Vertical gravity applied to particles (0.0 means no gravity).               |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of individual particles in seconds.              |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per burst.                  |
| `render_on_grid`          | Whether particles should be rendered on the game grid.                      |
| `fade_based_on_lifetime`  | If particles fade out as their lifetime decreases.                          |
| `area_circle_radius.min`, `area_circle_radius.max` | Radius of the emission area (0 means point emission).                       |
| `airflow_force`, `airflow_time`, `airflow_scale` | Parameters controlling airflow effects on particles.                        |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Interval between particle emissions in frames.                              |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles.                                         |
| `image_animation_file`    | Path to the image animation file for the particle's appearance.             |
| `image_animation_speed`   | Speed of the image animation.                                               |
| `image_animation_loop`    | Whether the image animation should loop.                                    |
| `is_emitting`             | Whether the emitter is currently active.                                    |

### LifetimeComponent

Defines the overall lifetime of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of the entity in seconds. |

### AudioComponent

Handles the sound effects associated with this entity.

| Attribute    | Description                                       |
| :----------- | :------------------------------------------------ |
| `file`       | Path to the audio bank file.                      |
| `event_root` | The root event name for the audio playback.       |