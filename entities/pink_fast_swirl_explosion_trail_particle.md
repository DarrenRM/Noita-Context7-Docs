---
title: Pink Fast Swirl Explosion Trail Particle
category: entities
---

# Pink Fast Swirl Explosion Trail Particle

This document describes the configuration for a specific particle effect used in Noita, designed to create a fast-swirling pink trail during explosions.

## Entity Configuration

The core of this particle effect is defined within an `<Entity>` tag, which contains various components that dictate its behavior and appearance.

### Key Components and Attributes

Here are the most important components and their attributes that define this particle:

*   **`<VelocityComponent>`**: Manages the particle's movement.
    *   `gravity_y="0"`: The particle is not affected by gravity.
    *   `air_friction="2"`: Applies a moderate amount of air friction.
    *   `updates_velocity="1"`: Enables velocity updates.

*   **`<SimplePhysicsComponent>`**: Provides basic physics simulation for the particle.

*   **`<SetStartVelocityComponent>`**: Defines the initial velocity of the particles.
    *   `randomize_speed.min="450"`: Minimum initial speed.
    *   `randomize_speed.max="600"`: Maximum initial speed.
    *   `randomize_angle.min="0"`: Minimum initial angle (in radians).
    *   `randomize_angle.max="6.283185"`: Maximum initial angle (full circle).

*   **`<ParticleEmitterComponent>`**: Controls the emission of particles.
    *   `emitted_material_name="plasma_fading_pink"`: Specifies the material of the emitted particles.
    *   `delay_frames="2"`: A short delay before emission starts.
    *   `gravity.y="0"`: Emitted particles are not affected by gravity.
    *   `count_min="0"`: Minimum number of particles to emit per interval.
    *   `count_max="1"`: Maximum number of particles to emit per interval.
    *   `lifetime_min="0.5"`: Minimum lifetime of emitted particles.
    *   `lifetime_max="2.5"`: Maximum lifetime of emitted particles.
    *   `emit_real_particles="0"`: This is a cosmetic particle, not a physical one.
    *   `render_on_grid="0"`: Particle is not rendered on the game grid.
    *   `is_trail="1"`: This emitter is designed to create a trail effect.
    *   `trail_gap="1"`: The spacing between trail segments.
    *   `airflow_force="0.3"`: The force applied by airflow.
    *   `airflow_time="0.01"`: Duration of airflow effect.
    *   `airflow_scale="0.22"`: Scale of the airflow effect.
    *   `emit_cosmetic_particles="1"`: Emits cosmetic particles.
    *   `emission_interval_min_frames="1"`: Minimum frames between emissions.
    *   `emission_interval_max_frames="1"`: Maximum frames between emissions.
    *   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime decreases.
    *   `is_emitting="1"`: The emitter is active.

*   **`<LifetimeComponent>`**: Defines the lifetime of the entity itself.
    *   `lifetime="100"`: Base lifetime of the entity.
    *   `randomize_lifetime.min="-75"`: Minimum randomization for lifetime.
    *   `randomize_lifetime.max="75"`: Maximum randomization for lifetime.

*   **`<LuaComponent>`**: Integrates custom Lua scripting.
    *   `script_source_file="data/scripts/particles/swirl_movement.lua"`: Specifies the Lua script responsible for the swirling movement.
    *   `execute_every_n_frame="1"`: The script executes every frame.

### Summary of Behavior

This particle entity is configured to emit a single, fast-moving pink plasma particle with a short lifespan. The `SetStartVelocityComponent` ensures a wide range of initial speeds and angles, creating a dynamic burst. The `ParticleEmitterComponent` is set up to act as a trail, with a small gap between segments, and it utilizes airflow to influence the particle's movement. Crucially, the `LuaComponent` points to `swirl_movement.lua`, indicating that custom logic is applied to achieve the characteristic swirling motion of this trail. The overall entity has a relatively long lifetime, allowing the trail effect to persist for a noticeable duration.