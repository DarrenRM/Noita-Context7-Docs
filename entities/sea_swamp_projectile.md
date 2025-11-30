---
title: Sea Swamp Projectile
category: entities
---

# Sea Swamp Projectile

This entity defines a projectile that spawns "swamp" material. It's designed to create a localized area of swamp, likely for environmental effects or damage.

## Key Components

### MaterialSeaSpawnerComponent

This component is responsible for spawning the "swamp" material.

| Attribute         | Description                                                                 |
| :---------------- | :-------------------------------------------------------------------------- |
| `size.x`          | Width of the area where swamp material is spawned.                          |
| `size.y`          | Height of the area where swamp material is spawned.                         |
| `offset.x`        | Horizontal offset for the spawn area.                                       |
| `offset.y`        | Vertical offset for the spawn area.                                         |
| `speed`           | Speed at which the swamp material is spawned or spreads.                    |
| `noise_threshold` | Threshold for noise generation, affecting the distribution of the material. |
| `material`        | The name of the material to spawn (e.g., "swamp").                          |

### LifetimeComponent

Determines how long the projectile (and its spawned material) persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration in frames the projectile lasts. |

### ParticleEmitterComponent

Manages the visual particles associated with the projectile, contributing to the "swamp" effect.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | The material name for the particles being emitted (should match `MaterialSeaSpawnerComponent`).         |
| `gravity.y`               | Vertical gravity applied to the emitted particles. `0.0` means no gravity.                              |
| `lifetime_min`            | Minimum lifetime of individual particles.                                                               |
| `lifetime_max`            | Maximum lifetime of individual particles.                                                               |
| `count_min`               | Minimum number of particles emitted per emission cycle.                                                 |
| `count_max`               | Maximum number of particles emitted per emission cycle.                                                 |
| `render_on_grid`          | Whether particles should be rendered on the game grid.                                                  |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                                                 |
| `airflow_force`           | The force of airflow affecting the particles.                                                           |
| `airflow_time`            | Duration for which airflow affects particles.                                                           |
| `airflow_scale`           | Scale of the airflow effect.                                                                            |
| `image_animation_file`    | Path to the image file used for particle animation.                                                     |
| `image_animation_speed`   | Speed of the particle image animation.                                                                  |
| `is_emitting`             | If `1`, the particle emitter is active.                                                                 |

### MusicEnergyAffectorComponent

This component influences the game's music energy.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `energy_target` | The target energy level for the music system. |

### AudioComponent

Handles the sound effects associated with the projectile.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `file`          | Path to the audio bank file.                                             |
| `event_root`    | The root event name for the projectile's sound effects.                  |
| `set_latest_event_position` | If `1`, the sound event will be positioned at the projectile's location. |