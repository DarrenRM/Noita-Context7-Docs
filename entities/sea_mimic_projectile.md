---
title: Sea Mimic Projectile
category: entities
---

# Sea Mimic Projectile

This document details the configuration for the "Sea Mimic" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is defined as a player projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
    <!-- Components follow -->
</Entity>
```

## Key Components

### MaterialSeaSpawnerComponent

This component is responsible for spawning the "mimic_liquid" material.

| Attribute          | Description                                                              |
| :----------------- | :----------------------------------------------------------------------- |
| `size.x`           | Width of the spawn area.                                                 |
| `size.y`           | Height of the spawn area.                                                |
| `offset.x`         | Horizontal offset for the spawn area.                                    |
| `offset.y`         | Vertical offset for the spawn area.                                      |
| `speed`            | Speed at which the material is spawned.                                  |
| `noise_threshold`  | Threshold for noise-based spawning (0.0 means no noise effect).          |
| `material`         | The name of the material to spawn (e.g., `mimic_liquid`).                |

### LifetimeComponent

Determines how long the projectile (and its spawned effects) will persist.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| Duration in frames before the entity is destroyed. |

### ParticleEmitterComponent

Manages the visual particles associated with the projectile.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `emitted_material_name`   | The material name for the emitted particles.                             |
| `gravity.y`               | Vertical gravity applied to particles.                                   |
| `lifetime_min`            | Minimum lifetime of individual particles.                                |
| `lifetime_max`            | Maximum lifetime of individual particles.                                |
| `count_min`               | Minimum number of particles emitted per burst.                           |
| `count_max`               | Maximum number of particles emitted per burst.                           |
| `render_on_grid`          | Whether particles should render on the game grid.                        |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases.                  |
| `area_circle_radius.min`  | Minimum radius of the emission circle.                                   |
| `area_circle_radius.max`  | Maximum radius of the emission circle.                                   |
| `cosmetic_force_create`   | Whether to force cosmetic particle creation.                             |
| `airflow_force`           | Force applied by airflow.                                                |
| `airflow_time`            | Duration airflow affects particles.                                      |
| `airflow_scale`           | Scale of the airflow effect.                                             |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                             |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                             |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles.                                      |
| `image_animation_file`    | Path to the particle image animation file.                               |
| `image_animation_speed`   | Speed of the particle image animation.                                   |
| `image_animation_loop`    | Whether the particle image animation should loop.                        |
| `is_emitting`             | Whether the particle emitter is currently active.                        |

### MusicEnergyAffectorComponent

This component influences energy levels, likely related to game mechanics.

| Attribute     | Description                                  |
| :------------ | :------------------------------------------- |
| `energy_target` | The target energy level to affect.           |

### AudioComponent

Handles the sound effects for the projectile.

| Attribute          | Description                                                              |
| :----------------- | :----------------------------------------------------------------------- |
| `file`             | Path to the audio bank file.                                             |
| `event_root`       | The root event name for the projectile's sound.                          |
| `set_latest_event_position` | Whether to set the sound event's position to the projectile's location. |