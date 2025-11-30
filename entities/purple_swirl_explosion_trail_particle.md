---
title: Purple Swirl Explosion Trail Particle
category: entities
---

# Purple Swirl Explosion Trail Particle

This document describes the configuration for a particle entity in Noita, specifically designed to create a purple, swirling trail effect during explosions.

## Entity Configuration

The core of this particle is defined by its components, which dictate its physical behavior, emission properties, and visual characteristics.

### Key Components and Attributes

*   **`VelocityComponent`**: Manages the particle's velocity.
    *   `gravity_y="0"`: The particle is not affected by gravity.
    *   `air_friction="2"`: Applies a moderate amount of air friction.
    *   `updates_velocity="1"`: Enables velocity updates.

*   **`SimplePhysicsComponent`**: Provides basic physics simulation for the particle.

*   **`SetStartVelocityComponent`**: Defines the initial velocity of the particle upon emission.
    *   `randomize_speed.min="150"`: Minimum initial speed.
    *   `randomize_speed.max="300"`: Maximum initial speed.
    *   `randomize_angle.min="0"`: Minimum initial angle (in radians).
    *   `randomize_angle.max="6.283185"`: Maximum initial angle (full circle).

*   **`ParticleEmitterComponent`**: Controls the emission of other particles.
    *   `emitted_material_name="spark_purple_bright"`: The material of the particles to be emitted.
    *   `delay_frames="6"`: Delay in frames before emitting the first particle.
    *   `gravity.y="0"`: Emitted particles are not affected by gravity.
    *   `friction="10"`: Friction applied to emitted particles.
    *   `count_min="0"`: Minimum number of particles to emit per burst.
    *   `count_max="1"`: Maximum number of particles to emit per burst.
    *   `lifetime_min="0.5"`: Minimum lifetime of emitted particles.
    *   `lifetime_max="5.5"`: Maximum lifetime of emitted particles.
    *   `emit_real_particles="0"`: This is a cosmetic particle emitter.
    *   `render_on_grid="0"`: The emitter itself is not rendered on the grid.
    *   `is_trail="1"`: Indicates this emitter is part of a trail effect.
    *   `trail_gap="1"`: Spacing between trail segments.
    *   `airflow_force="0.3"`: Force applied by airflow.
    *   `airflow_time="0.01"`: Duration of airflow effect.
    *   `airflow_scale="0.22"`: Scale of the airflow effect.
    *   `emit_cosmetic_particles="1"`: Emits cosmetic particles.
    *   `emission_interval_min_frames="1"`: Minimum interval between emissions.
    *   `emission_interval_max_frames="1"`: Maximum interval between emissions.
    *   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime decreases.
    *   `is_emitting="1"`: The emitter is active.

*   **`LifetimeComponent`**: Manages the lifetime of the particle entity itself.
    *   `lifetime="100"`: Base lifetime of the entity.
    *   `randomize_lifetime.min="-75"`: Minimum randomization of lifetime.
    *   `randomize_lifetime.max="75"`: Maximum randomization of lifetime.

*   **`LuaComponent`**: Executes a Lua script for custom behavior.
    *   `script_source_file="data/scripts/particles/swirl_movement.lua"`: Specifies the Lua script responsible for the swirling movement.
    *   `execute_every_n_frame="1"`: The script executes every frame.

### Summary

This particle entity is designed to be a visual effect, likely triggered by an explosion. It doesn't have gravity and is given an initial velocity. Its primary function is to emit smaller "spark\_purple\_bright" particles in a trail, with the overall movement and swirling behavior controlled by an external Lua script (`swirl_movement.lua`). The `LifetimeComponent` ensures the particle entity itself exists for a variable duration, allowing the trail effect to persist.