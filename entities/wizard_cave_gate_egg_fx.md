---
title: Wizard Cave Gate Egg FX
category: entities
---

# Wizard Cave Gate Egg FX

This entity defines visual effects for the Wizard Cave Gate, specifically an "egg" like particle emission. It utilizes two `ParticleEmitterComponent` instances to create distinct particle behaviors.

## Key Components

### ParticleEmitterComponent (Primary Emission)

This component handles the initial, more intense burst of particles.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`       | `spark_red_bright` - The material used for the emitted particles.           |
| `gravity.y`                   | `0.0` - Particles are not affected by gravity.                              |
| `x_vel_min`, `x_vel_max`      | `0` - No horizontal velocity.                                               |
| `y_vel_min`, `y_vel_max`      | `0` - No vertical velocity.                                                 |
| `friction`                    | `2.1` - Moderate friction applied to particles.                             |
| `count_min`, `count_max`      | `1` to `8` - A small number of particles are emitted per burst.             |
| `lifetime_min`, `lifetime_max`| `2.25` to `5.0` - Particles have a relatively short lifespan.               |
| `area_circle_radius.min/max`  | `1` - Particles are emitted from a very small circular area.                |
| `emit_real_particles`         | `0` - Only cosmetic particles are emitted.                                  |
| `render_on_grid`              | `1` - Particles are rendered on the game grid.                              |
| `fade_based_on_lifetime`      | `1` - Particles fade out as their lifetime decreases.                       |
| `emit_cosmetic_particles`     | `1` - Ensures cosmetic particles are emitted.                               |
| `velocity_always_away_from_center` | `70` - Particles are strongly pushed away from the emission center.       |
| `emission_interval_min/max_frames` | `1` - Particles are emitted continuously with no delay between frames. |
| `is_emitting`                 | `1` - The emitter is active.                                                |

### ParticleEmitterComponent (Secondary Emission)

This component creates a more sustained, outward-spreading effect.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`       | `spark_red_bright` - Same material as the primary emission.                 |
| `gravity.y`                   | `0.0` - Particles are not affected by gravity.                              |
| `x_vel_min`, `x_vel_max`      | `0` - No horizontal velocity.                                               |
| `y_vel_min`, `y_vel_max`      | `0` - No vertical velocity.                                                 |
| `friction`                    | `0.8` - Lower friction, allowing particles to travel further.               |
| `count_min`, `count_max`      | `30` to `50` - A larger number of particles are emitted per burst.          |
| `lifetime_min`, `lifetime_max`| `5.25` to `9.0` - Particles have a longer lifespan.                         |
| `area_circle_radius.min/max`  | `4` - Particles are emitted from a slightly larger circular area.           |
| `emit_real_particles`         | `0` - Only cosmetic particles are emitted.                                  |
| `render_on_grid`              | `1` - Particles are rendered on the game grid.                              |
| `fade_based_on_lifetime`      | `1` - Particles fade out as their lifetime decreases.                       |
| `emit_cosmetic_particles`     | `1` - Ensures cosmetic particles are emitted.                               |
| `velocity_always_away_from_center` | `-30` - Particles are pushed away from the emission center, but with less force than the primary emission. |
| `emission_interval_min/max_frames` | `12` - Particles are emitted with a slight delay between bursts.        |
| `is_emitting`                 | `1` - The emitter is active.                                                |

### LifetimeComponent

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| `25` - The total duration this entity exists. |