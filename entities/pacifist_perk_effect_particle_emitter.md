---
title: Pacifist Perk Effect Particle Emitter
category: entities
---

# Pacifist Perk Effect Particle Emitter

This entity defines the visual and functional effects associated with the Pacifist perk in Noita. It primarily uses a `ParticleEmitterComponent` to create visual sparks and a `MagicConvertMaterialComponent` to alter the environment.

## Key Components

### ParticleEmitterComponent

This component is responsible for generating visual particles.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`    | The material of the particles to be emitted (e.g., `spark_yellow`).         |
| `gravity.y`                | The vertical gravity applied to the particles. `0.0` means no gravity.      |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifetime of individual particles in seconds.        |
| `count_min`, `count_max`   | The minimum and maximum number of particles emitted per emission.           |
| `render_on_grid`           | Whether the particles should be rendered on the game grid. `1` means yes.   |
| `fade_based_on_lifetime`   | Whether particles should fade out as their lifetime decreases. `1` means yes. |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the emission area. `0` means particles are emitted from a single point. |
| `airflow_force`, `airflow_time`, `airflow_scale` | Parameters controlling how particles are affected by airflow.             |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The frame interval between particle emissions. `1` means continuous emission. |
| `emit_cosmetic_particles`  | Whether to emit cosmetic particles. `1` means yes.                          |
| `image_animation_file`     | The image file used for animating particles.                                |
| `image_animation_raytrace_from_center` | Whether the animation should raytrace from the center of the image. `1` means yes. |
| `image_animation_speed`    | The speed of the particle image animation.                                  |
| `image_animation_loop`     | Whether the particle image animation should loop. `0` means no loop.        |
| `is_emitting`              | Whether the particle emitter is currently active. `1` means yes.            |

### LifetimeComponent

Determines the overall lifetime of the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The total lifetime of the entity in seconds. |

### MagicConvertMaterialComponent

This component allows the entity to convert one material into another within a specified radius.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `_enabled`        | Whether the component is enabled. `1` means yes.                         |
| `kill_when_finished` | Whether the entity should be killed when the conversion is finished. `0` means no. |
| `from_material`   | The material to be converted from (e.g., `glowstone`).                   |
| `steps_per_frame` | The number of conversion steps to perform per frame.                     |
| `to_material`     | The material to convert to (e.g., `water`).                              |
| `radius`          | The radius around the entity within which material conversion occurs.    |

### AudioComponent

Handles the sound effects associated with the entity.

| Attribute   | Description                                    |
| :---------- | :--------------------------------------------- |
| `file`      | The audio bank file.                           |
| `event_root` | The root event path for the perk's sound cues. |