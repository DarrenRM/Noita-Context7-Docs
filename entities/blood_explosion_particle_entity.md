---
title: Blood Explosion Particle Entity
category: entities
---

# Blood Explosion Particle Entity

This entity defines the visual and behavioral aspects of a blood explosion effect in Noita. It's primarily composed of particle emitters that generate blood splatters and fading blood particles.

## Key Components

### ProjectileComponent
This component dictates the projectile-like behavior of the entity.

*   `lifetime`: The duration (in frames) before the entity triggers its `on_lifetime_out_explode` event.
*   `on_lifetime_out_explode`: Set to `1`, meaning the entity will explode when its lifetime expires.
*   Other explosion-related parameters are set to `0`, indicating no direct damage, camera shake, or hole creation from this component itself.

### SpriteParticleEmitterComponent
This component is responsible for emitting sprite-based particles, likely for the initial blood splatters.

*   `sprite_file`: Specifies the sprite files to be used for the particles. It uses a pattern `bloodsplatter_large_$[1-3].xml` to randomly select from three variations.
*   `count_min`, `count_max`: The minimum and maximum number of particles to emit.
*   `lifetime`: Set to `0`, suggesting the sprites are managed by their own internal lifetimes.
*   `color`: Initial color of the particles (white in this case).
*   `color_change`: The alpha component (`a`) is set to `-2`, indicating a gradual fading out.
*   `gravity.y`: Set to `10`, causing particles to fall.
*   `randomize_rotation`: Particles will have random initial rotations.
*   `randomize_position`: Particles are emitted within a small random area around the origin.
*   `randomize_angular_velocity`: Particles will have random initial angular velocities.
*   `randomize_velocity`: Particles are emitted with random velocities in X and Y directions.

### ParticleEmitterComponent (Blood)
This component generates "blood" material particles.

*   `emitted_material_name`: Set to `"blood"`, defining the material of the emitted particles.
*   `lifetime_min`, `lifetime_max`: The duration (in frames) for these blood particles.
*   `count_min`, `count_max`: The number of particles to emit.
*   `area_circle_radius.max`: The maximum radius within which particles are emitted.
*   `gravity.y`: Set to `0.0`, meaning these particles are not affected by gravity.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These parameters suggest a subtle influence of airflow on the particles.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines the range of initial velocities for the emitted particles.
*   `fade_based_on_lifetime`: Set to `1`, indicating particles will fade as their lifetime progresses.

### ParticleEmitterComponent (Blood Fading)
This component generates "blood\_fading" material particles, likely for a more persistent or distinct fading effect.

*   `emitted_material_name`: Set to `"blood_fading"`, defining the material.
*   `lifetime_min`, `lifetime_max`: These particles have a significantly longer lifetime.
*   `count_min`, `count_max`: The number of particles to emit.
*   `area_circle_radius.max`: The maximum radius for emission.
*   `create_real_particles`, `emit_real_particles`: These are set to `1`, indicating these are actual game particles.
*   `emit_cosmetic_particles`: Set to `0`, meaning these are not cosmetic effects.
*   `gravity.y`: Set to `0.0`, no gravity effect.