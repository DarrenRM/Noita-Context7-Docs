---
title: Quantum Split FX Red Die
category: entities
---

# Quantum Split FX Red Die

This entity defines a visual effect for when a quantum split occurs, specifically a "red die" effect. It primarily uses a `ParticleEmitterComponent` to generate red sparks.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles that create the visual effect.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_red_bright` | The material used for the emitted particles (bright red sparks).            |
| `gravity.y`               | `0.0`        | Particles have no vertical gravity.                                         |
| `x_vel_min`, `x_vel_max`  | `0`          | Particles have no initial horizontal velocity.                               |
| `y_vel_min`, `y_vel_max`  | `0`          | Particles have no initial vertical velocity.                                |
| `friction`                | `2.2`        | The amount of friction applied to the particles.                            |
| `count_min`, `count_max`  | `10` - `20`  | The number of particles emitted per burst.                                  |
| `lifetime_min`, `lifetime_max` | `1.25` - `3.0` | The duration each particle exists.                                          |
| `area_circle_radius.min/max` | `4`          | Particles are emitted within a small circular area.                         |
| `emit_real_particles`     | `0`          | Indicates that these are not "real" physics particles.                      |
| `render_on_grid`          | `1`          | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`          | Particles fade out as their lifetime decreases.                             |
| `emit_cosmetic_particles` | `1`          | These are cosmetic particles, not affecting gameplay mechanics.             |
| `velocity_always_away_from_center` | `-30`        | Particles are pushed away from the emission center.                         |
| `emission_interval_min/max_frames` | `1`          | Particles are emitted continuously with no delay between emissions.         |
| `is_emitting`             | `1`          | The particle emitter is active.                                             |

### LifetimeComponent

This component defines the overall lifespan of the entity itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `2`   | The entity exists for 2 seconds.          |