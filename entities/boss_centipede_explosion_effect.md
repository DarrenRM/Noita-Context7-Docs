---
title: Boss Centipede Explosion Effect
category: entities
---

# Boss Centipede Explosion Effect

This entity defines the visual and functional aspects of the explosion effect when the Boss Centipede dies. It primarily uses a `ProjectileComponent` to manage the explosion's timing and a `ParticleEmitterComponent` to generate visual particles.

## Key Components

### ProjectileComponent

This component dictates how the explosion behaves.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `_enabled`             | Whether the component is active (1 for enabled).                            |
| `lifetime`             | The duration (in seconds) before the projectile triggers its `on_lifetime_out_explode` event. |
| `on_lifetime_out_explode` | If set to 1, the projectile will explode when its lifetime expires.         |
| `damage`               | Base damage of the projectile (set to 0 for this effect).                   |

#### config_explosion

This nested element configures the specifics of the explosion itself.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `never_cache`             | If 1, this explosion will not be cached, ensuring it's always generated fresh. |
| `damage`                  | Damage dealt by the explosion (set to 0).                                   |
| `camera_shake`            | Intensity of camera shake (set to 0).                                       |
| `explosion_radius`        | The radius of the explosion (set to 0).                                     |
| `particle_effect`         | Whether to create particle effects (set to 0).                              |
| `damage_mortals`          | Whether the explosion damages living entities (set to 0).                   |
| `physics_explosion_power` | Maximum power of the physics-based explosion (set to 0).                    |
| `physics_throw_enabled`   | Whether physics objects are thrown by the explosion (set to 0).             |

### ParticleEmitterComponent

This component is responsible for generating the visual particles that make up the explosion's appearance.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material name of the particles to emit (e.g., "plasma_fading").         |
| `gravity.y`               | The gravitational pull on the particles in the Y-axis.                      |
| `lifetime_min`            | Minimum lifetime of individual particles.                                   |
| `lifetime_max`            | Maximum lifetime of individual particles.                                   |
| `count_min`               | Minimum number of particles emitted per emission cycle.                     |
| `count_max`               | Maximum number of particles emitted per emission cycle.                     |
| `area_circle_radius.max`  | The maximum radius of the circular area from which particles are emitted.   |
| `airflow_force`           | The force applied by airflow to the particles.                              |
| `airflow_time`            | The duration for which airflow affects particles.                           |
| `x_vel_min`               | Minimum initial velocity in the X-axis.                                     |
| `x_vel_max`               | Maximum initial velocity in the X-axis.                                     |
| `y_vel_min`               | Minimum initial velocity in the Y-axis.                                     |
| `y_vel_max`               | Maximum initial velocity in the Y-axis.                                     |
| `is_emitting`             | Whether the emitter is currently active (1 for active).                     |