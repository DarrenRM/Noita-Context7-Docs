---
title: Orange Slow Swirl Explosion Trail Particle
category: entities
---

# Orange Slow Swirl Explosion Trail Particle

This document describes the configuration for a specific particle effect in Noita, designed to create a slow, swirling orange trail during explosions.

## Entity Configuration

The core of this particle effect is defined within an `<Entity>` tag, containing various components that dictate its behavior and appearance.

### Key Components and Attributes

Here are the most important components and their attributes that define this particle:

#### VelocityComponent

Controls the particle's movement and how it interacts with forces like gravity and air friction.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
*   `air_friction="2"`: Applies a moderate amount of air friction, slowing the particle over time.
*   `updates_velocity="1"`: Enables the velocity component to actively update the particle's movement.

#### SimplePhysicsComponent

A basic physics component that allows the particle to interact with the game's physics engine.

#### SetStartVelocityComponent

Determines the initial velocity of the particles when they are spawned.

*   `randomize_speed.min="50"`: The minimum initial speed of the particle.
*   `randomize_speed.max="200"`: The maximum initial speed of the particle.
*   `randomize_angle.min="0"`: The minimum initial angle (in radians) for the particle's velocity.
*   `randomize_angle.max="6.283185"`: The maximum initial angle (in radians) for the particle's velocity (a full circle).

#### ParticleEmitterComponent

This is the primary component responsible for generating and managing the particles.

*   `emitted_material_name="spark"`: The material used for the spawned particles (likely a default spark effect).
*   `delay_frames="2"`: A short delay before the first particle is emitted.
*   `gravity.y="0"`: Particles emitted by this emitter are not affected by gravity.
*   `friction="10"`: A high friction value applied to emitted particles, causing them to slow down quickly.
*   `count_min="0"`: Minimum number of particles to emit per emission cycle.
*   `count_max="1"`: Maximum number of particles to emit per emission cycle.
*   `lifetime_min="0.5"`: Minimum lifetime of an emitted particle in seconds.
*   `lifetime_max="2.5"`: Maximum lifetime of an emitted particle in seconds.
*   `emit_real_particles="0"`: This emitter does not emit "real" particles that interact with the world; they are cosmetic.
*   `render_on_grid="0"`: Particles are not rendered on the game grid.
*   `is_trail="1"`: This emitter is configured to create a trail effect.
*   `trail_gap="1"`: The spacing between particles in the trail.
*   `airflow_force="0.3"`: A moderate force applied by airflow.
*   `airflow_time="0.01"`: The duration airflow affects particles.
*   `airflow_scale="0.22"`: The scale of the airflow effect.
*   `emit_cosmetic_particles="1"`: Ensures these are cosmetic particles.
*   `emission_interval_min_frames="1"`: Minimum interval between emissions in frames.
*   `emission_interval_max_frames="1"`: Maximum interval between emissions in frames.
*   `fade_based_on_lifetime="1"`: Particles will fade out as their lifetime decreases.
*   `is_emitting="1"`: The emitter is active and will produce particles.

#### LifetimeComponent

Determines the overall lifetime of the entity itself, which in turn affects how long the emitter can operate.

*   `lifetime="100"`: The base lifetime of the entity in seconds.
*   `randomize_lifetime.min="-75"`: Minimum randomization for the entity's lifetime.
*   `randomize_lifetime.max="35"`: Maximum randomization for the entity's lifetime.

#### LuaComponent

Integrates custom Lua scripting to control particle behavior.

*   `script_source_file="data/scripts/particles/swirl_movement.lua"`: Specifies the Lua script responsible for the swirling movement.
*   `execute_every_n_frame="1"`: The Lua script will execute every frame.

## Associated Lua Script

The `swirl_movement.lua` script (located at `data/scripts/particles/swirl_movement.lua`) is crucial for achieving the unique swirling motion of these particles. This script would typically handle:

*   Applying rotational forces to particles.
*   Modifying particle velocity to create a spiral or swirl pattern.
*   Potentially adjusting particle behavior based on their age or proximity to other particles.

**Note:** The exact implementation within `swirl_movement.lua` is not detailed here but is essential for the visual effect.