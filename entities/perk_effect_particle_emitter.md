---
title: Perk Effect Particle Emitter
category: entities
---

# Perk Effect Particle Emitter

This entity defines a particle emitter used to create visual effects associated with perks in Noita. It utilizes an image animation for particle appearance and can also trigger material conversion and sound effects.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`    | The material of the particles being emitted (e.g., `spark_blue`).           |
| `gravity.y`                | Vertical gravity applied to particles. `0.0` means no gravity.              |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of individual particles in seconds.              |
| `count_min`, `count_max`   | Minimum and maximum number of particles emitted per burst.                  |
| `render_on_grid`           | Whether particles should be rendered on the game grid. `1` means yes.       |
| `fade_based_on_lifetime`   | Whether particles fade out as their lifetime decreases. `1` means yes.      |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular emission area. `0` means emission at a single point. |
| `airflow_force`            | The force of airflow affecting particles.                                   |
| `airflow_time`             | The duration airflow affects particles.                                     |
| `airflow_scale`            | The scale of the airflow effect.                                            |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The frame interval between particle emissions. `1` means continuous emission. |
| `emit_cosmetic_particles`  | Whether to emit cosmetic particles. `1` means yes.                          |
| `image_animation_file`     | Path to the image file used for particle animation.                         |
| `image_animation_raytrace_from_center` | Whether the animation should raytrace from the center of the image. `1` means yes. |
| `image_animation_speed`    | The speed of the image animation.                                           |
| `image_animation_loop`     | Whether the image animation should loop. `0` means no loop.                 |
| `is_emitting`              | Whether the emitter is currently active. `1` means yes.                     |

### LifetimeComponent

Determines the overall lifetime of the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The total lifetime of the entity in seconds. |

### MagicConvertMaterialComponent

This component allows the entity to convert one material into another within a specified radius.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `_enabled`      | Whether the component is active. `1` means enabled.                      |
| `kill_when_finished` | Whether the entity should be destroyed when the conversion is finished. `0` means no. |
| `from_material` | The material to be converted from (e.g., `glowstone`).                   |
| `steps_per_frame` | The number of conversion steps to perform per frame.                     |
| `to_material`   | The material to convert to (e.g., `blood`).                              |
| `radius`        | The radius within which the material conversion occurs.                  |

### AudioComponent

This component plays a sound effect when the entity is active.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The path to the audio bank file.                                         |
| `event_root` | The root event name within the audio bank to trigger (e.g., `event_cues/perk`). |