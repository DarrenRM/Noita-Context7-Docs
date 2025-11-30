---
title: Ember Trail Particle
category: entities/particles
---

# Ember Trail Particle

This document describes the configuration for the `ember_trail.xml` entity, which defines a particle effect used to create an ember trail.

## Entity Components

The `ember_trail.xml` entity is composed of several components that dictate its behavior and appearance.

### VelocityComponent

Controls the particle's movement and interaction with physics.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `gravity_y`    | The gravitational pull on the particle in the Y-axis. |
| `air_friction` | The resistance the particle experiences from air. |
| `liquid_death_threshold` | The threshold at which the particle dies in liquid. |

### SimplePhysicsComponent

Enables basic physics simulation for the particle.

### SetStartVelocityComponent

Defines the initial velocity of the particle.

| Attribute              | Description                                     |
|------------------------|-------------------------------------------------|
| `randomize_speed.min`  | Minimum initial speed.                          |
| `randomize_speed.max`  | Maximum initial speed.                          |
| `randomize_angle.min`  | Minimum initial angle (in radians).             |
| `randomize_angle.max`  | Maximum initial angle (in radians).             |

### SpriteComponent

Determines the visual representation of the particle.

| Attribute    | Description                                     |
|--------------|-------------------------------------------------|
| `image_file` | Path to the sprite image file.                  |
| `additive`   | Whether the sprite uses additive blending.      |
| `emissive`   | Whether the sprite emits light.                 |
| `alpha`      | The transparency of the sprite.                 |

### ParticleEmitterComponent

Manages the emission of particles. This is the core component for creating the trail effect.

| Attribute                     | Description                                                              |
|-------------------------------|--------------------------------------------------------------------------|
| `emitted_material_name`       | The material of the particles to be emitted (e.g., "fire").              |
| `delay_frames`                | Frames to wait before emitting the first particle.                       |
| `gravity.y`                   | Gravitational pull on emitted particles.                                 |
| `x_vel_min`, `x_vel_max`      | Minimum and maximum X velocity of emitted particles.                     |
| `y_vel_min`, `y_vel_max`      | Minimum and maximum Y velocity of emitted particles.                     |
| `friction`                    | Friction applied to emitted particles.                                   |
| `count_min`, `count_max`      | Minimum and maximum number of particles emitted per burst.               |
| `lifetime_min`, `lifetime_max`| Minimum and maximum lifetime of emitted particles.                       |
| `emit_real_particles`         | Whether to emit actual game entities or just visual particles.           |
| `is_trail`                    | Indicates if this emitter is creating a trail.                           |
| `trail_gap`                   | The spacing between particles in the trail.                              |
| `airflow_force`               | The force of airflow affecting emitted particles.                        |
| `airflow_time`                | Duration of airflow effect.                                              |
| `airflow_scale`               | Scale of the airflow effect.                                             |
| `emit_cosmetic_particles`     | Whether to emit cosmetic particles (visual only).                        |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Minimum and maximum frames between emissions. |
| `fade_based_on_lifetime`      | Whether particles fade out as their lifetime decreases.                  |
| `is_emitting`                 | Whether the emitter is currently active.                                 |

### LifetimeComponent

Determines the lifespan of the entity itself.

| Attribute               | Description                                     |
|-------------------------|-------------------------------------------------|
| `lifetime`              | The base lifespan of the entity.                |
| `randomize_lifetime.min`| Minimum random variation in lifespan.           |
| `randomize_lifetime.max`| Maximum random variation in lifespan.           |

### LuaComponent

Allows for custom Lua scripting to control entity behavior.

| Attribute             | Description                                     |
|-----------------------|-------------------------------------------------|
| `script_source_file`  | Path to the Lua script file.                    |
| `remove_after_executed`| Whether to remove the Lua component after execution. |