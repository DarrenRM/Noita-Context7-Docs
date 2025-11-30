---
title: Sea Acid Gas Projectile
category: entities
---

# Sea Acid Gas Projectile

This document details the configuration for the "Sea Acid Gas" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity

The projectile is based on the `$projectile_default` entity and is tagged as `projectile_player`.

## Key Components

### MaterialSeaSpawnerComponent

This component dictates the spawning of the sea acid gas material.

| Attribute        | Value   | Description                                                              |
| :--------------- | :------ | :----------------------------------------------------------------------- |
| `size.x`         | `300`   | Width of the spawning area.                                              |
| `size.y`         | `256`   | Height of the spawning area.                                             |
| `offset.x`       | `0`     | Horizontal offset for the spawning area.                                 |
| `offset.y`       | `158`   | Vertical offset for the spawning area.                                   |
| `speed`          | `10`    | The speed at which the material is spawned or moves.                     |
| `noise_threshold`| `0.0`   | Threshold for noise-based spawning (0.0 means no noise influence).       |
| `material`       | `acid_gas`| The specific material to be spawned.                                     |

### LifetimeComponent

Determines how long the projectile (and its spawned effects) will persist.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `300` | The duration in frames the projectile lasts. |

### ParticleEmitterComponent

Manages the visual particles that constitute the acid gas effect.

| Attribute                 | Value   | Description                                                              |
| :------------------------ | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name`   | `acid`  | The material name of the particles being emitted.                        |
| `gravity.y`               | `0.0`   | Vertical gravity applied to particles (0.0 means no gravity).            |
| `lifetime_min`            | `6`     | Minimum lifetime of individual particles in frames.                      |
| `lifetime_max`            | `8`     | Maximum lifetime of individual particles in frames.                      |
| `count_min`               | `8`     | Minimum number of particles emitted per emission.                        |
| `count_max`               | `8`     | Maximum number of particles emitted per emission.                        |
| `render_on_grid`          | `1`     | Whether particles should be rendered on the game grid.                   |
| `fade_based_on_lifetime`  | `1`     | Whether particles fade out as their lifetime decreases.                  |
| `airflow_force`           | `0.51`  | The force applied by airflow to the particles.                           |
| `airflow_time`            | `1.01`  | The duration airflow affects particles.                                  |
| `airflow_scale`           | `0.05`  | The scaling factor for airflow effects.                                  |
| `image_animation_file`    | `data/particles/image_emitters/sea_acid.png` | The texture file for animated particles. |
| `image_animation_speed`   | `5`     | The speed of the particle image animation.                               |
| `image_animation_loop`    | `0`     | Whether the particle image animation should loop.                        |
| `is_emitting`             | `1`     | Whether the particle emitter is active.                                  |

### MusicEnergyAffectorComponent

This component influences the player's energy.

| Attribute     | Value | Description                                                              |
| :------------ | :---- | :----------------------------------------------------------------------- |
| `energy_target`| `1.0` | The target energy level this component aims to affect (1.0 is full energy). |

### AudioComponent

Handles the sound effects associated with the projectile.

| Attribute          | Value                                 | Description                                                              |
| :----------------- | :------------------------------------ | :----------------------------------------------------------------------- |
| `file`             | `data/audio/Desktop/projectiles.bank` | The audio bank file containing the sound events.                         |
| `event_root`       | `player_projectiles/sea_of_acid`      | The root event name for the projectile's sound.                          |
| `set_latest_event_position` | `1`                                   | Whether to set the sound event's position to the projectile's latest position. |