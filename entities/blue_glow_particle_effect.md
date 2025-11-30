---
title: Blue Glow Particle Effect
category: entities
---

# Blue Glow Particle Effect

This entity defines a particle effect that generates blue glowing sparks. It's primarily used for visual flair and doesn't have direct gameplay impact like damage or collision.

## Key Components

### ProjectileComponent
This component defines the behavior of the entity as a projectile, though in this case, it's configured to not interact physically or deal damage.

*   `lifetime`: The duration in seconds before the projectile is destroyed. Set to `10`.
*   `on_lifetime_out_explode`: If `1`, the projectile will explode when its lifetime ends. Set to `1`.
*   `damage`: The amount of damage this projectile deals. Set to `0`.
*   `speed_min`, `speed_max`: The minimum and maximum speed of the projectile. Both set to `0`, indicating no movement.
*   `die_on_low_velocity`, `on_death_explode`, `on_death_gfx_leave_sprite`, `on_collision_die`: All set to `0`, meaning no special actions occur on death or collision.

### ParticleEmitterComponent (Primary)
This component is responsible for emitting the main burst of blue sparks.

*   `emitted_material_name`: The material of the particles to be emitted. Set to `"spark_blue"`.
*   `lifetime_min`, `lifetime_max`: The minimum and maximum lifetime of individual particles in seconds. Set to `0.3` and `0.8` respectively.
*   `count_min`, `count_max`: The minimum and maximum number of particles emitted per emission. Set to `30` and `40`.
*   `area_circle_radius.min`, `area_circle_radius.max`: The minimum and maximum radius of the circular area from which particles are emitted. Set to `1` and `2`.
*   `gravity.y`: The gravitational pull on the particles in the Y-axis. Set to `0.0`, meaning no gravity.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters controlling airflow effects on particles. Set to `1.5`, `1.9`, and `0.15`.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: The range of initial velocities for emitted particles. Set to `-1` to `1` for both X and Y.
*   `velocity_always_away_from_center`: A value that influences particles to move away from the emission center. Set to `180`.
*   `is_emitting`: If `1`, the emitter is active. Set to `1`.

### ParticleEmitterComponent (Secondary)
This component emits a sparser, longer-lasting set of blue sparks.

*   `emitted_material_name`: Set to `"spark_blue"`.
*   `lifetime_min`, `lifetime_max`: The minimum and maximum lifetime of individual particles in seconds. Set to `5.5` and `15.5`.
*   `count_min`, `count_max`: The minimum and maximum number of particles emitted per emission. Set to `1` and `4`.
*   `area_circle_radius.max`: The maximum radius of the circular emission area. Set to `12`.
*   `gravity.y`: Set to `0.0`.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Set to `0.5`, `1.9`, and `0.15`.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: The range of initial velocities for emitted particles. Set to `-20` to `20` for both X and Y, allowing for more spread.
*   `is_emitting`: Set to `1`.

---

**Note:** The `VelocityComponent` is present but empty, indicating it doesn't contribute any specific velocity behavior to the entity itself, as its movement is handled by the particle emitters.