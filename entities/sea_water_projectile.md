---
title: Sea Water Projectile
category: entities
---

# Sea Water Projectile

This document details the configuration for the "Sea Water" projectile entity in Noita, focusing on its spawning, particle emission, and audio properties.

## Entity Configuration

The core entity is defined as a player projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
    <!-- ... components ... -->
</Entity>
```

## Key Components

### MaterialSeaSpawnerComponent

This component controls the spawning of the "water" material.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `size.x`         | Width of the spawning area.                                              |
| `size.y`         | Height of the spawning area.                                             |
| `offset.x`       | Horizontal offset for the spawning area.                                 |
| `offset.y`       | Vertical offset for the spawning area.                                   |
| `speed`          | The speed at which the material is spawned.                              |
| `noise_threshold`| Threshold for noise-based spawning (0.0 means no noise influence).       |
| `material`       | The material to be spawned (in this case, "water").                      |

### LifetimeComponent

Determines how long the projectile entity persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration in frames the entity exists. |

### ParticleEmitterComponent

Manages the emission of visual particles that constitute the projectile's appearance.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | The material name of the particles being emitted ("water").                                             |
| `gravity.y`               | Vertical gravity applied to the particles (0.0 means no gravity).                                       |
| `lifetime_min`            | Minimum lifetime of emitted particles in frames.                                                        |
| `lifetime_max`            | Maximum lifetime of emitted particles in frames.                                                        |
| `count_min`               | Minimum number of particles emitted per emission cycle.                                                 |
| `count_max`               | Maximum number of particles emitted per emission cycle.                                                 |
| `render_on_grid`          | Whether particles should be rendered on the game grid.                                                  |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases.                                                 |
| `airflow_force`           | The strength of airflow affecting the particles.                                                        |
| `airflow_time`            | Duration for which airflow affects particles.                                                           |
| `airflow_scale`           | Scale factor for airflow effects.                                                                       |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                                                              |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                                                              |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (visual effects not affecting gameplay).                             |
| `image_animation_file`    | Path to the image animation file for the particles.                                                     |
| `image_animation_speed`   | Speed of the particle image animation.                                                                  |
| `image_animation_loop`    | Whether the particle image animation should loop.                                                       |
| `is_emitting`             | Whether the particle emitter is currently active.                                                       |

### MusicEnergyAffectorComponent

This component influences some form of energy target, likely related to game mechanics.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `energy_target` | The target energy value (1.0 suggests full energy or a specific state). |

### AudioComponent

Handles the sound effects associated with the projectile.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `file`            | Path to the audio bank file.                                             |
| `event_root`      | The root event name for the projectile's sound effects.                  |
| `set_latest_event_position` | Whether to set the sound event's position to the latest known position. |