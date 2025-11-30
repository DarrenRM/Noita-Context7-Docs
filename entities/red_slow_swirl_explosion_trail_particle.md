---
title: Red Slow Swirl Explosion Trail Particle
category: entities
---

# Red Slow Swirl Explosion Trail Particle

This entity defines a particle effect used in explosions, specifically a slow-moving, red, swirling trail. It's designed to be emitted as part of a larger explosion effect.

## Key Components

### `VelocityComponent`

Controls the basic physics of the particle.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `gravity_y`    | Vertical gravity applied to the particle.       |
| `air_friction` | Resistance to movement in the air.              |
| `updates_velocity` | Whether this component actively updates velocity. |

### `SimplePhysicsComponent`

A basic physics component, likely for simpler interactions.

### `SetStartVelocityComponent`

Determines the initial velocity of the emitted particles.

| Attribute             | Description                                       |
|-----------------------|---------------------------------------------------|
| `randomize_speed.min` | Minimum initial speed.                            |
| `randomize_speed.max` | Maximum initial speed.                            |
| `randomize_angle.min` | Minimum initial angle (in radians).               |
| `randomize_angle.max` | Maximum initial angle (in radians).               |

### `ParticleEmitterComponent`

The core component responsible for emitting particles.

| Attribute                 | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| `emitted_material_name`   | The material/entity to be emitted (e.g., `spark_red`).                      |
| `delay_frames`            | Frames to wait before emitting the first particle.                          |
| `gravity.y`               | Gravity applied to emitted particles.                                       |
| `friction`                | Friction applied to emitted particles.                                      |
| `count_min` / `count_max` | Range for the number of particles emitted per emission.                     |
| `lifetime_min` / `lifetime_max` | Range for the lifespan of emitted particles.                                |
| `emit_real_particles`     | Whether to emit actual game entities or just visual particles.              |
| `is_trail`                | Marks this emitter as creating a trail effect.                              |
| `trail_gap`               | Spacing between particles in the trail.                                     |
| `airflow_force`           | Strength of airflow affecting emitted particles.                            |
| `airflow_time`            | Duration airflow affects particles.                                         |
| `airflow_scale`           | Scale of the airflow effect.                                                |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (visual only).                           |
| `emission_interval_min_frames` / `emission_interval_max_frames` | Interval between emissions.                                                 |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases.                     |
| `is_emitting`             | Whether the emitter is currently active.                                    |

### `LifetimeComponent`

Controls the lifespan of the emitter itself.

| Attribute             | Description                                       |
|-----------------------|---------------------------------------------------|
| `lifetime`            | Base lifespan of the emitter.                     |
| `randomize_lifetime.min` | Minimum randomization for the emitter's lifespan. |
| `randomize_lifetime.max` | Maximum randomization for the emitter's lifespan. |

### `LuaComponent`

Attaches a Lua script to control custom behavior.

| Attribute           | Description                                       |
|---------------------|---------------------------------------------------|
| `script_source_file`| Path to the Lua script file (`swirl_movement.lua`). |
| `execute_every_n_frame` | How often the script is executed (every 1 frame). |

## Associated Scripts

*   `data/scripts/particles/swirl_movement.lua`: This script is crucial for the "swirl" effect. It likely manipulates the velocity or position of the emitted particles over time to create a swirling motion.

---