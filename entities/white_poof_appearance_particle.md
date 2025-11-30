---
title: White Poof Appearance Particle
category: entities
---

# White Poof Appearance Particle

This entity defines a particle effect that creates a "white poof" appearance, typically used for visual feedback on entity creation or certain events.

## Key Components

### ProjectileComponent

This component governs the projectile-like behavior of the particle emitter itself.

| Attribute               | Description                                                                 |
| :---------------------- | :-------------------------------------------------------------------------- |
| `_enabled`              | Whether the component is active.                                            |
| `speed_min`, `speed_max`| Minimum and maximum speed. Set to 0, indicating no inherent projectile speed. |
| `lifetime`              | Duration in seconds before the emitter itself is destroyed.                 |
| `on_lifetime_out_explode`| If true, the emitter will explode when its lifetime ends. Set to 1.         |
| `damage`                | Damage dealt by the projectile. Set to 0, as this is a visual effect.       |

#### config_explosion

Configuration for the explosion that occurs when `on_lifetime_out_explode` is true.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `damage`              | Damage dealt by the explosion. Set to 0.                                    |
| `explosion_radius`    | Radius of the explosion. Set to 0.                                          |
| `particle_effect`     | Whether to create particle effects from the explosion. Set to 0.            |
| `damage_mortals`      | Whether the explosion damages mortals. Set to 0.                            |
| `physics_explosion_power.max` | Maximum physics force applied by the explosion. Set to 0.               |

### ParticleEmitterComponent

This component is responsible for generating the actual visual particles.

| Attribute                 | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`       | The material name of the particles to emit. Set to "spark_white".           |
| `gravity.y`                   | Vertical gravity applied to emitted particles. Set to 20.0.                 |
| `lifetime_min`, `lifetime_max`| Minimum and maximum lifetime in seconds for individual particles.           |
| `count_min`, `count_max`      | Minimum and maximum number of particles emitted per emission cycle.         |
| `render_on_grid`              | Whether particles should render on the game grid. Set to 1.                 |
| `fade_based_on_lifetime`      | Whether particles fade out as their lifetime decreases. Set to 1.           |
| `area_circle_radius.max`      | Maximum radius of the circular area from which particles are emitted.       |
| `airflow_force`               | Force applied by airflow.                                                   |
| `airflow_time`                | Duration airflow affects particles.                                         |
| `airflow_scale`               | Scale of the airflow effect.                                                |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Frames between particle emissions. Set to 1 for continuous emission. |
| `emit_cosmetic_particles`     | Whether to emit cosmetic particles. Set to 1.                               |
| `x_vel_min`, `x_vel_max`      | Minimum and maximum horizontal velocity for emitted particles.              |
| `y_vel_min`, `y_vel_max`      | Minimum and maximum vertical velocity for emitted particles.                |
| `is_emitting`                 | Whether the emitter is currently active. Set to 1.                          |