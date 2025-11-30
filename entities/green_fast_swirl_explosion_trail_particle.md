---
title: Green Fast Swirl Explosion Trail Particle
category: entities
---

# Green Fast Swirl Explosion Trail Particle

This document describes the configuration for a particle entity in Noita, specifically designed to create a fast-swirling green trail effect during explosions.

## Entity Configuration

The core of this particle is defined by its components, each contributing to its behavior and appearance.

### Key Components and Attributes

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
    *   `air_friction="2"`: Applies a moderate amount of air friction, slowing the particle over time.
    *   `updates_velocity="1"`: Enables the velocity component to actively update the particle's movement.

*   **`SimplePhysicsComponent`**:
    *   This component is present, indicating basic physics interactions, though no specific parameters are set here.

*   **`SetStartVelocityComponent`**:
    *   `randomize_speed.min="450"`: The minimum initial speed of the particle.
    *   `randomize_speed.max="600"`: The maximum initial speed of the particle.
    *   `randomize_angle.min="0"`: The minimum initial angle of the particle's velocity (in radians).
    *   `randomize_angle.max="6.283185"`: The maximum initial angle of the particle's velocity (approximately 2π radians, covering a full circle).

*   **`ParticleEmitterComponent`**: This is the primary component responsible for emitting the actual visual particles.
    *   `emitted_material_name="spark_green"`: Specifies the material of the particles to be emitted (green sparks).
    *   `delay_frames="2"`: A short delay before the emitter starts.
    *   `gravity.y="0"`: Emitted particles are not affected by gravity.
    *   `friction="10"`: High friction applied to emitted particles, causing them to slow down quickly.
    *   `count_min="0"`, `count_max="1"`: Emits either 0 or 1 particle per emission cycle.
    *   `lifetime_min="0.5"`, `lifetime_max="2.5"`: The lifespan of each emitted particle in seconds.
    *   `emit_real_particles="0"`: This particle emitter does not emit "real" particles that interact with the game world; it's for cosmetic effects.
    *   `render_on_grid="0"`: The particles are not rendered on the game grid.
    *   `is_trail="1"`: This emitter is configured to create a trail effect.
    *   `trail_gap="1"`: The spacing between particles in the trail.
    *   `airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.22"`: Parameters related to airflow influence on the emitted particles, contributing to the swirling motion.
    *   `emit_cosmetic_particles="1"`: Ensures these are treated as cosmetic effects.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: Particles are emitted every frame.
    *   `fade_based_on_lifetime="1"`: Emitted particles will fade out as their lifetime decreases.
    *   `is_emitting="1"`: The emitter is active.

*   **`LifetimeComponent`**:
    *   `lifetime="100"`: The base lifetime of the entity itself (in seconds).
    *   `randomize_lifetime.min="-75"`, `randomize_lifetime.max="75"`: Randomizes the entity's lifetime, making it vary.

*   **`LuaComponent`**:
    *   `script_source_file="data/scripts/particles/swirl_movement.lua"`: Links to an external Lua script that dictates the swirling movement of the particles.
    *   `execute_every_n_frame="1"`: The Lua script is executed every frame, allowing for dynamic movement updates.

### Summary

This entity defines a particle that, when spawned, immediately sets a high initial velocity. It then acts as an emitter for green spark particles. These emitted particles have a short lifespan, high friction, and are influenced by airflow, creating a fast, swirling trail effect. The `swirl_movement.lua` script is crucial for achieving the characteristic swirling motion. The overall entity has a long, randomized lifetime, ensuring the trail effect persists for a noticeable duration.