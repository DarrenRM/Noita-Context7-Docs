---
title: Sea Acid Projectile
category: entities
---

# Sea Acid Projectile

This document details the configuration of the "Sea Acid" projectile entity in Noita, focusing on its spawning, particle emission, and audio properties.

## Entity Definition

The core entity is defined as a player projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
    <!-- ... components ... -->
</Entity>
```

## Key Components

### MaterialSeaSpawnerComponent

This component controls the spawning of the "sea" material, specifically acid in this case.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `size.x`         | Width of the spawned material area.                                      |
| `size.y`         | Height of the spawned material area.                                     |
| `offset.x`       | Horizontal offset for the spawned material.                              |
| `offset.y`       | Vertical offset for the spawned material.                                |
| `speed`          | The speed at which the material is spawned or spreads.                   |
| `noise_threshold`| Threshold for noise generation, affecting material distribution.         |
| `material`       | The type of material to spawn (e.g., "acid").                            |

### LifetimeComponent

Determines how long the projectile entity exists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration in frames the entity persists. |

### ParticleEmitterComponent

Manages the visual particles that constitute the projectile's effect.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | The material of the particles being emitted (e.g., "acid").                                             |
| `gravity.y`               | Vertical gravity applied to the particles. `0.0` means no gravity.                                      |
| `lifetime_min`            | Minimum lifetime of individual particles in frames.                                                     |
| `lifetime_max`            | Maximum lifetime of individual particles in frames.                                                     |
| `count_min`               | Minimum number of particles emitted per emission cycle.                                                 |
| `count_max`               | Maximum number of particles emitted per emission cycle.                                                 |
| `render_on_grid`          | Whether particles should be rendered on the game grid.                                                  |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                                                 |
| `area_circle_radius.min`  | Minimum radius of the emission area (circle). `0` means a point emission.                               |
| `area_circle_radius.max`  | Maximum radius of the emission area (circle). `0` means a point emission.                               |
| `airflow_force`           | Strength of airflow affecting particles.                                                                |
| `airflow_time`            | Duration airflow affects particles.                                                                     |
| `airflow_scale`           | Scale of airflow effect.                                                                                |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                                                              |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                                                              |
| `emit_cosmetic_particles` | If `1`, emits cosmetic particles (visual flair).                                                        |
| `image_animation_file`    | Path to the sprite sheet for animated particles.                                                        |
| `image_animation_speed`   | Speed of the particle image animation.                                                                  |
| `collide_with_gas_and_fire` | If `0`, particles do not interact with gas or fire.                                                     |
| `image_animation_loop`    | If `0`, the particle animation does not loop.                                                           |
| `is_emitting`             | If `1`, the particle emitter is active.                                                                 |

### MusicEnergyAffectorComponent

This component influences some form of "energy" related to music, likely for game mechanics or visual feedback.

| Attribute     | Description                                  |
| :------------ | :------------------------------------------- |
| `energy_target` | The target value for the energy effect.      |

### AudioComponent

Defines the sound effects associated with the projectile.

| Attribute            | Description                                                              |
| :------------------- | :----------------------------------------------------------------------- |
| `file`               | Path to the audio bank file.                                             |
| `event_root`         | The root event name for the sound effect (e.g., "player_projectiles/sea_of_acid"). |
| `set_latest_event_position` | If `1`, the sound event's position will be set to the latest event position. |