---
title: Spell Refresh Effect Particle Emitter
category: entities/particles
---

# Spell Refresh Effect Particle Emitter

This entity defines the visual and auditory effects that play when a spell is refreshed. It utilizes a `ParticleEmitterComponent` to generate animated particles and an `AudioComponent` to play a sound cue.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles that create the visual effect.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`    | The material of the particles to be emitted (e.g., "spark_teal").           |
| `gravity.y`                | The gravitational pull on the particles along the y-axis. `0.0` means no gravity. |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of individual particles in seconds.        |
| `count_min`, `count_max`   | The minimum and maximum number of particles emitted per emission.           |
| `render_on_grid`           | Whether the particles should be rendered on the game grid. `1` means yes.     |
| `fade_based_on_lifetime`   | Whether particles should fade out as their lifetime decreases. `1` means yes. |
| `area_circle_radius.min`, `area_circle_radius.max` | The minimum and maximum radius of the circular emission area. `0` means emission at a single point. |
| `airflow_force`            | The force applied by airflow to the particles.                              |
| `airflow_time`             | The duration for which airflow affects the particles.                       |
| `airflow_scale`            | The scaling factor for the airflow effect.                                  |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The minimum and maximum frames between particle emissions. `1` means continuous emission. |
| `emit_cosmetic_particles`  | Whether to emit cosmetic particles. `1` means yes.                          |
| `image_animation_file`     | The path to the image file used for particle animation.                     |
| `image_animation_speed`    | The speed of the image animation.                                           |
| `image_animation_loop`     | Whether the image animation should loop. `0` means no loop.                 |
| `image_animation_raytrace_from_center` | Whether the animation should raytrace from the center of the image. `1` means yes. |
| `is_emitting`              | Whether the emitter is currently active. `1` means yes.                     |

### LifetimeComponent

This component defines the total lifespan of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The total lifespan of the entity in seconds. |

### AudioComponent

This component handles the sound effect associated with the spell refresh.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The path to the audio bank file.                                         |
| `event_root` | The root event name within the audio bank to be triggered (e.g., "event_cues/spell_refresh"). |