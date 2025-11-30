---
title: Wand Effect Particle Emitter
category: entities/particles
---

# Wand Effect Particle Emitter

This entity defines a particle emitter used for wand effects in Noita. It utilizes an animated image to create visual effects and can also trigger material conversions and play sounds.

## Key Components and Attributes

### ParticleEmitterComponent

This component controls the emission of particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles being emitted (e.g., "spark_green").          |
| `gravity.y`               | Vertical gravity applied to particles (0.0 means no gravity).               |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of individual particles in seconds.              |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per emission event.         |
| `render_on_grid`          | Whether particles should be rendered on the game grid (1 for yes).          |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases (1 for yes).         |
| `area_circle_radius.min`, `area_circle_radius.max` | Radius of the emission area. 0 means particles emit from a single point. |
| `airflow_force`           | Force applied by airflow to particles.                                      |
| `airflow_time`            | Duration airflow affects particles.                                         |
| `airflow_scale`           | Scale of the airflow effect.                                                |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Interval between particle emissions in frames. |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (1 for yes).                             |
| `image_animation_file`    | Path to the image file used for particle animation.                         |
| `image_animation_speed`   | Speed of the image animation.                                               |
| `image_animation_raytrace_from_center` | Whether animation rays originate from the center (1 for yes). |
| `image_animation_loop`    | Whether the image animation should loop (0 for no).                         |
| `is_emitting`             | Whether the emitter is currently active (1 for yes).                        |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The total lifetime of the entity in seconds. |

### MagicConvertMaterialComponent

This component allows the entity to convert one material into another within a specified radius.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `_enabled`      | Whether the component is active (1 for yes).                             |
| `kill_when_finished` | Whether the entity is destroyed after conversion is complete (0 for no). |
| `from_material` | The material to be converted.                                            |
| `steps_per_frame` | How many conversion steps occur per frame.                               |
| `to_material`   | The material to convert to.                                              |
| `radius`        | The radius within which the material conversion occurs.                  |

### AudioComponent

This component plays audio events associated with the entity.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `file`      | The path to the audio bank file.                |
| `event_root` | The root event name for the audio cue.          |