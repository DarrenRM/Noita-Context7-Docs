---
title: Green Swirl Explosion Trail Particle
category: entities
---

# Green Swirl Explosion Trail Particle

This entity defines a particle that creates a green, swirling trail effect, often used in explosions. It utilizes a combination of physics, particle emission, and a custom Lua script for its movement.

## Key Components

### VelocityComponent
This component governs the basic physics of the particle.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `gravity_y`    | Vertical gravity applied to the particle (0 means no gravity). |
| `air_friction` | Resistance to movement in the air.              |
| `updates_velocity` | Whether this component actively updates velocity. |

### SimplePhysicsComponent
A basic physics component, likely enabling interaction with other physics objects.

### SetStartVelocityComponent
This component defines the initial velocity of the emitted particles.

| Attribute             | Description                                                              |
|-----------------------|--------------------------------------------------------------------------|
| `randomize_speed.min` | Minimum initial speed of the particle.                                   |
| `randomize_speed.max` | Maximum initial speed of the particle.                                   |
| `randomize_angle.min` | Minimum initial angle (in radians) of the particle's velocity.           |
| `randomize_angle.max` | Maximum initial angle (in radians) of the particle's velocity.           |

### ParticleEmitterComponent
This is the core component responsible for generating and managing the trail particles.

| Attribute                 | Description                                                                                                |
|---------------------------|------------------------------------------------------------------------------------------------------------|
| `emitted_material_name`   | The material of the particles to be emitted (e.g., "spark_green").                                       |
| `delay_frames`            | Number of frames to wait before emitting the first particle.                                               |
| `gravity.y`               | Vertical gravity applied to emitted particles.                                                             |
| `x_vel_min`, `x_vel_max`  | Minimum and maximum horizontal velocity of emitted particles.                                              |
| `y_vel_min`, `y_vel_max`  | Minimum and maximum vertical velocity of emitted particles.                                                |
| `friction`                | Friction applied to emitted particles.                                                                     |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per emission event.                                        |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of emitted particles.                                                         |
| `emit_real_particles`     | Whether to emit actual game entities or just visual effects (0 for visual effects).                        |
| `is_trail`                | Indicates that this emitter is creating a trail effect (1 for true).                                       |
| `trail_gap`               | Spacing between particles in the trail.                                                                    |
| `airflow_force`           | Strength of airflow affecting the particles.                                                               |
| `airflow_time`            | Duration of airflow effect.                                                                                |
| `airflow_scale`           | Scale of the airflow effect.                                                                               |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (visual effects only).                                                  |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Minimum and maximum frames between emission events.                                                        |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases.                                                    |
| `is_emitting`             | Whether the emitter is currently active.                                                                   |

### LifetimeComponent
Determines the overall lifetime of the entity that spawns these particles.

| Attribute             | Description                                                              |
|-----------------------|--------------------------------------------------------------------------|
| `lifetime`            | Base lifetime of the entity.                                             |
| `randomize_lifetime.min` | Minimum random variation to the entity's lifetime.                       |
| `randomize_lifetime.max` | Maximum random variation to the entity's lifetime.                       |

### LuaComponent
This component allows for custom scripting to control particle behavior.

| Attribute           | Description                                                              |
|---------------------|--------------------------------------------------------------------------|
| `script_source_file`| Path to the Lua script file that controls particle behavior.             |
| `execute_every_n_frame` | How often the Lua script should execute (1 means every frame).           |

## Associated Scripts

*   `data/scripts/particles/swirl_movement.lua`: This script is crucial for defining the swirling motion of the particles. It likely manipulates particle velocities and positions over time to achieve the desired visual effect.