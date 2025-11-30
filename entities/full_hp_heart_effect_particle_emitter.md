---
title: Full HP Heart Effect Particle Emitter
category: entities
---

# Full HP Heart Effect Particle Emitter

This entity defines a particle effect that plays when the player reaches full HP. It utilizes an image animation for its visual representation and emits red sparks.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_red`  | The material of the particles being emitted.                                |
| `gravity.y`               | `0.0`        | No vertical gravity applied to the emitted particles.                       |
| `lifetime_min`            | `8`          | Minimum lifetime of each emitted particle in seconds.                       |
| `lifetime_max`            | `15`         | Maximum lifetime of each emitted particle in seconds.                       |
| `count_min`               | `8`          | Minimum number of particles emitted per emission.                           |
| `count_max`               | `8`          | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`          | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`          | Particles fade out as their lifetime decreases.                             |
| `area_circle_radius.min`  | `0`          | Minimum radius of the emission area (a single point).                       |
| `area_circle_radius.max`  | `0`          | Maximum radius of the emission area (a single point).                       |
| `airflow_force`           | `0.251`      | Force applied by airflow to the particles.                                  |
| `airflow_time`            | `1.01`       | Duration for which airflow affects particles.                               |
| `airflow_scale`           | `0.05`       | Scale of the airflow effect.                                                |
| `emission_interval_min_frames` | `1`      | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1`      | Maximum frames between particle emissions.                                  |
| `emit_cosmetic_particles` | `1`          | Emits cosmetic particles (visual effects not affecting gameplay).           |
| `image_animation_file`    | `data/particles/image_emitters/heart_effect.png` | Path to the image file used for particle animation.                       |
| `image_animation_speed`   | `5`          | Speed of the image animation (frames per second).                           |
| `image_animation_loop`    | `0`          | Animation does not loop.                                                    |
| `image_animation_raytrace_from_center` | `1` | Raytracing for animation starts from the center of the image.             |
| `is_emitting`             | `1`          | The emitter is active and emitting particles.                               |

### LifetimeComponent

This component defines the total lifetime of the entity.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `260` | The total lifetime of the entity in seconds. |

### AudioComponent

This component plays a sound effect when the entity is active.

| Attribute   | Value                                  | Description                                     |
| :---------- | :------------------------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/event_cues.bank`   | The audio bank file containing the event.       |
| `event_root`| `event_cues/heart_fullhp`              | The specific audio event to trigger.            |