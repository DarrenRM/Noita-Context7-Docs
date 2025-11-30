---
title: Pink Swirl Explosion Trail Particle
category: entities
---

# Pink Swirl Explosion Trail Particle

This document describes the configuration for a particle entity in Noita, specifically designed to create a pink, swirling trail effect often associated with explosions.

## Entity Configuration

The core of this particle is defined by its components, each contributing to its behavior and appearance.

### Key Components and Attributes

*   **`VelocityComponent`**: Manages the particle's movement.
    *   `gravity_y="0"`: The particle is not affected by gravity.
    *   `air_friction="2"`: Applies a moderate amount of air friction, slowing the particle over time.
    *   `updates_velocity="1"`: Enables velocity updates based on other components.

*   **`SimplePhysicsComponent`**: Provides basic physics simulation for the particle.

*   **`SetStartVelocityComponent`**: Defines the initial velocity of the particle.
    *   `randomize_speed.min="50"`: Minimum initial speed.
    *   `randomize_speed.max="250"`: Maximum initial speed.
    *   `randomize_angle.min="0"`: Minimum initial angle (in radians).
    *   `randomize_angle.max="6.283185"`: Maximum initial angle (full circle in radians).

*   **`ParticleEmitterComponent`**: This is the primary component responsible for emitting the actual visual particles.
    *   `emitted_material_name="plasma_fading_pink"`: Specifies the material of the particles to be emitted, which is a fading pink plasma.
    *   `delay_frames="6"`: A delay in frames before the emitter starts.
    *   `gravity.y="0"`: The emitted particles are not affected by gravity.
    *   `x_vel_min="0"`, `x_vel_max="0"`, `y_vel_min="0"`, `y_vel_max="0"`: The initial velocity of emitted particles is zero, meaning their movement is dictated by other factors.
    *   `friction="10"`: High friction applied to emitted particles, causing them to slow down quickly.
    *   `count_min="0"`, `count_max="1"`: Emits between 0 and 1 particle per emission cycle.
    *   `lifetime_min="0.3"`, `lifetime_max="2.0"`: The lifespan of each emitted particle in seconds.
    *   `emit_real_particles="0"`: This indicates that the emitted particles are cosmetic and not physical entities.
    *   `render_on_grid="0"`: The particles are not rendered on the game grid.
    *   `is_trail="1"`: This particle acts as a trail emitter.
    *   `trail_gap="1"`: The spacing between trail segments.
    *   `airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.22"`: Parameters related to airflow effects on the emitted particles, contributing to their movement.
    *   `emit_cosmetic_particles="1"`: Ensures cosmetic particles are emitted.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: The emitter fires every frame.
    *   `fade_based_on_lifetime="1"`: The particles fade out as their lifetime decreases.
    *   `is_emitting="1"`: The emitter is active.

*   **`LifetimeComponent`**: Controls the lifespan of the entity itself.
    *   `lifetime="75"`: The base lifespan of the entity in seconds.
    *   `randomize_lifetime.min="-50"`, `randomize_lifetime.max="50"`: Randomizes the entity's lifespan within a range.

*   **`LuaComponent`**: Integrates custom Lua scripting for advanced behavior.
    *   `script_source_file="data/scripts/particles/swirl_movement.lua"`: This is the crucial part that defines the swirling motion. It points to an external Lua script responsible for manipulating the particle's velocity and position to create the swirl effect.
    *   `execute_every_n_frame="1"`: The Lua script is executed every frame.

### Summary of Behavior

This entity acts as a source for a trail of pink, fading plasma particles. It is not affected by gravity and has a defined lifespan. The `SetStartVelocityComponent` gives it an initial random push, while the `ParticleEmitterComponent` continuously emits particles with specific properties like friction and airflow. The most significant aspect is the `LuaComponent` which links to `swirl_movement.lua`, indicating that the characteristic swirling motion is achieved through custom scripting, likely manipulating the velocity of the emitted particles to create a vortex-like pattern.