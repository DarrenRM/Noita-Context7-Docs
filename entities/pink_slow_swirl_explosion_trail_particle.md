---
title: Pink Slow Swirl Explosion Trail Particle
category: entities
---

# Pink Slow Swirl Explosion Trail Particle

This document describes the configuration for a specific particle effect in Noita, designed to create a slow, swirling pink trail as part of an explosion.

## Entity Configuration

The core of this particle effect is defined within the `<Entity>` tag.

### Key Components and Attributes

This particle utilizes several components to define its behavior, appearance, and emission.

#### VelocityComponent

Controls the basic physics of the particle.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
*   `air_friction="2"`: Applies a moderate amount of air friction.
*   `updates_velocity="1"`: Enables velocity updates based on physics.

#### SimplePhysicsComponent

A basic physics component, likely used in conjunction with `VelocityComponent`.

#### SetStartVelocityComponent

Determines the initial velocity of the emitted particles.

*   `randomize_speed.min="50"`: Minimum initial speed.
*   `randomize_speed.max="200"`: Maximum initial speed.
*   `randomize_angle.min="0"`: Minimum initial angle (in radians).
*   `randomize_angle.max="6.283185"`: Maximum initial angle (full circle).

#### ParticleEmitterComponent

This is the primary component responsible for emitting the particles.

*   `emitted_material_name="plasma_fading_pink"`: Specifies the material of the particles being emitted.
*   `delay_frames="2"`: A short delay before emission starts.
*   `gravity.y="0"`: Particles are not affected by gravity.
*   `friction="10"`: High friction applied to emitted particles.
*   `count_min="0"`: Minimum particles emitted per interval.
*   `count_max="1"`: Maximum particles emitted per interval.
*   `lifetime_min="0.5"`: Minimum lifetime of emitted particles.
*   `lifetime_max="2.5"`: Maximum lifetime of emitted particles.
*   `emit_real_particles="0"`: Indicates these are cosmetic particles, not physical entities.
*   `render_on_grid="0"`: Particles are not rendered on the game grid.
*   `is_trail="1"`: This emitter is configured to create a trail effect.
*   `trail_gap="1"`: The spacing between trail segments.
*   `airflow_force="0.3"`: A force applied by airflow.
*   `airflow_time="0.01"`: Duration of airflow influence.
*   `airflow_scale="0.22"`: Scale of the airflow effect.
*   `emit_cosmetic_particles="1"`: Explicitly states cosmetic particles are emitted.
*   `emission_interval_min_frames="1"`: Minimum frames between emissions.
*   `emission_interval_max_frames="1"`: Maximum frames between emissions.
*   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime decreases.
*   `is_emitting="1"`: The emitter is active.

#### LifetimeComponent

Defines the lifespan of the entity itself (the emitter).

*   `lifetime="100"`: Base lifetime of the emitter.
*   `randomize_lifetime.min="-75"`: Minimum randomization for lifetime.
*   `randomize_lifetime.max="35"`: Maximum randomization for lifetime.

#### LuaComponent

Integrates custom Lua scripting for advanced particle behavior.

*   `script_source_file="data/scripts/particles/swirl_movement.lua"`: Specifies the Lua script responsible for the swirling movement.
*   `execute_every_n_frame="1"`: The script runs every frame.