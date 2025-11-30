---
title: Neutralized Tiny Particle Emitter
category: entities
---

# Neutralized Tiny Particle Emitter

This entity defines a particle effect that spawns small, neutral particles. It's primarily used for visual feedback when certain actions occur, rather than for direct gameplay impact.

## Key Components

### ProjectileComponent

This component defines the projectile-like behavior of the entity. In this case, it's configured to not move, not explode on low velocity or death, and to die after a set lifetime, triggering an explosion when the lifetime is out.

*   `_enabled`: `1` (Component is active)
*   `speed_min`: `0` (Minimum projectile speed)
*   `speed_max`: `0` (Maximum projectile speed)
*   `die_on_low_velocity`: `0` (Does not die when velocity is low)
*   `on_death_explode`: `0` (Does not explode on death)
*   `on_lifetime_out_explode`: `1` (Explodes when lifetime expires)
*   `on_collision_die`: `0` (Does not die on collision)
*   `damage`: `0` (Deals no damage)
*   `lifetime`: `2` (The entity exists for 2 seconds before exploding)

#### config_explosion

This sub-element configures the explosion that occurs when the `lifetime` of the `ProjectileComponent` expires.

*   `damage`: `0` (Explosion deals no damage)
*   `camera_shake`: `0` (No camera shake)
*   `explosion_radius`: `0` (No explosion radius)
*   `particle_effect`: `0` (No additional particle effects from the explosion)
*   `damage_mortals`: `0` (Does not damage living entities)
*   `physics_explosion_power.max`: `0` (No physics-based explosion force)
*   `sparks_enabled`: `0` (No sparks generated)
*   `stains_enabled`: `0` (No stains left behind)

### ParticleEmitterComponent (Blue Sparks)

This component is responsible for emitting cosmetic blue sparks.

*   `emitted_material_name`: `"spark_blue"` (The material of the particles to emit)
*   `gravity.y`: `0.0` (No vertical gravity affecting emitted particles)
*   `lifetime_min`: `1.0` (Minimum lifetime of emitted particles)
*   `lifetime_max`: `2.0` (Maximum lifetime of emitted particles)
*   `count_min`: `5` (Minimum number of particles emitted per interval)
*   `count_max`: `15` (Maximum number of particles emitted per interval)
*   `render_on_grid`: `1` (Particles are rendered on the game grid)
*   `fade_based_on_lifetime`: `1` (Particles fade out as their lifetime decreases)
*   `area_circle_radius.max`: `4` (Particles are emitted within a circle of radius 4)
*   `airflow_force`: `0.5` (Applies a slight force in the direction of airflow)
*   `airflow_time`: `1.9` (Duration of airflow effect)
*   `airflow_scale`: `0.15` (Magnitude of airflow effect)
*   `emission_interval_min_frames`: `1` (Minimum frames between emissions)
*   `emission_interval_max_frames`: `1` (Maximum frames between emissions)
*   `emit_cosmetic_particles`: `1` (Emits cosmetic particles)
*   `x_vel_min`: `-40` (Minimum horizontal velocity of emitted particles)
*   `x_vel_max`: `40` (Maximum horizontal velocity of emitted particles)
*   `y_vel_min`: `-40` (Minimum vertical velocity of emitted particles)
*   `y_vel_max`: `40` (Maximum vertical velocity of emitted particles)
*   `is_emitting`: `1` (The emitter is active)

### ParticleEmitterComponent (Purple Sparks)

This component emits brighter, longer-lasting purple sparks.

*   `emitted_material_name`: `"spark_purple_bright"` (The material of the particles to emit)
*   `gravity.y`: `0.0` (No vertical gravity affecting emitted particles)
*   `count_min`: `2` (Minimum number of particles emitted per interval)
*   `count_max`: `10` (Maximum number of particles emitted per interval)
*   `lifetime_min`: `5` (Minimum lifetime of emitted particles)
*   `lifetime_max`: `20` (Maximum lifetime of emitted particles)
*   `area_circle_radius.max`: `10` (Particles are emitted within a circle of radius 10)
*   `emission_interval_min_frames`: `1` (Minimum frames between emissions)
*   `emission_interval_max_frames`: `1` (Maximum frames between emissions)
*   `create_real_particles`: `1` (Creates actual game particles)
*   `emit_real_particles`: `1` (Emits real particles)
*   `emit_cosmetic_particles`: `0` (Does not emit cosmetic particles)
*   `is_emitting`: `1` (The emitter is active)