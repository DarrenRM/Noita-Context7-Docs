---
title: Gold Pickup Particles
category: entities
---

# Gold Pickup Particles

This entity defines the visual and physical properties of particles emitted when gold is picked up in Noita. It's designed to create a brief, sparkling effect.

## Key Components

### `VelocityComponent`

Controls the movement of the entity itself.

| Attribute     | Value | Description                               |
|---------------|-------|-------------------------------------------|
| `gravity_y`   | `0`   | No vertical gravity applied to the entity. |
| `air_friction`| `4.0` | Moderate air friction.                    |

### `SimplePhysicsComponent`

Enables basic physics interactions for the entity.

### `LifetimeComponent`

Determines how long the entity exists.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `lifetime`| `10`  | The entity will exist for 10 game frames. |

### `ParticleEmitterComponent`

This is the core component responsible for generating the gold pickup particles.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `emitted_material_name`   | `spark_yellow` | The material used for the emitted particles.                                |
| `gravity.y`               | `0.0`   | Emitted particles are not affected by gravity.                              |
| `lifetime_min`            | `0.8`   | Minimum lifetime of each emitted particle in seconds.                       |
| `lifetime_max`            | `1.8`   | Maximum lifetime of each emitted particle in seconds.                       |
| `x_pos_offset_min`        | `-3`    | Minimum horizontal offset from the emitter's position.                      |
| `x_pos_offset_max`        | `3`     | Maximum horizontal offset from the emitter's position.                      |
| `y_pos_offset_min`        | `-3`    | Minimum vertical offset from the emitter's position.                        |
| `y_pos_offset_max`        | `3`     | Maximum vertical offset from the emitter's position.                        |
| `x_vel_min`               | `-30`   | Minimum horizontal velocity of emitted particles.                           |
| `x_vel_max`               | `30`    | Maximum horizontal velocity of emitted particles.                           |
| `y_vel_min`               | `-30`   | Minimum vertical velocity of emitted particles.                             |
| `y_vel_max`               | `30`    | Maximum vertical velocity of emitted particles.                             |
| `count_min`               | `4`     | Minimum number of particles emitted per burst.                              |
| `count_max`               | `4`     | Maximum number of particles emitted per burst.                              |
| `render_on_grid`          | `1`     | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`     | Particles fade out as their lifetime decreases.                             |
| `cosmetic_force_create`   | `0`     | Particles are not forced to exist beyond their natural lifetime.            |
| `airflow_force`           | `0.3`   | Strength of airflow effect on particles.                                    |
| `airflow_time`            | `0.01`  | Duration of airflow effect.                                                 |
| `airflow_scale`           | `0.05`  | Scale of airflow effect.                                                    |
| `emission_interval_min_frames` | `1` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1` | Maximum frames between particle emissions.                                  |
| `emit_cosmetic_particles` | `1`     | Emits cosmetic particles (visual effects).                                  |
| `is_emitting`             | `1`     | The emitter is active and will produce particles.                           |

### `LightComponent`

Adds a light source to the particles.

| Attribute     | Value | Description                               |
|---------------|-------|-------------------------------------------|
| `_enabled`    | `1`   | The light component is enabled.           |
| `r`           | `228` | Red component of the light color.         |
| `g`           | `255` | Green component of the light color.       |
| `b`           | `70`  | Blue component of the light color.        |
| `radius`      | `48`  | The radius of the light.                  |
| `fade_out_time`| `2`   | Time it takes for the light to fade out.  |