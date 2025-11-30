---
title: Red Fast Swirl Explosion Trail Particle
category: entities
---

# Red Fast Swirl Explosion Trail Particle

This document describes the configuration for a specific particle effect used in Noita, designed to create a fast-moving, swirling red trail during explosions.

## Entity Configuration

The core of this particle effect is defined within an `<Entity>` tag.

### Key Components and Attributes

This particle utilizes several components to achieve its visual and behavioral characteristics.

#### VelocityComponent

Controls the basic movement properties of the particle.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
*   `air_friction="2"`: Applies a moderate amount of air friction, slowing the particle over time.
*   `updates_velocity="1"`: Enables the velocity to be updated by other components.

#### SimplePhysicsComponent

A basic physics component, likely used to interact with the environment if `collide_with_grid` were enabled (though it's not in this case).

#### SetStartVelocityComponent

Determines the initial velocity of the emitted particles.

*   `randomize_speed.min="450"`: The minimum initial speed of the particle.
*   `randomize_speed.max="500"`: The maximum initial speed of the particle.
*   `randomize_angle.min="0"`: The minimum initial angle (in radians).
*   `randomize_angle.max="6.283185"`: The maximum initial angle (full circle in radians).

#### ParticleEmitterComponent

This is the primary component responsible for generating and managing the particles.

*   `emitted_material_name="spark_red"`: Specifies the material/visual appearance of the emitted particles.
*   `delay_frames="3"`: A short delay before the first particle is emitted.
*   `gravity.y="0"`: Particles emitted by this emitter are not affected by gravity.
*   `friction="10"`: High friction applied to emitted particles, contributing to their rapid deceleration.
*   `count_min="0"`, `count_max="1"`: Emits a very small number of particles per emission cycle.
*   `lifetime_min="0.5"`, `lifetime_max="5.5"`: The duration each individual particle exists.
*   `emit_real_particles="0"`: Indicates these are not "real" physics particles but visual effects.
*   `collide_with_grid="0"`: Particles do not interact with the game's grid/terrain.
*   `render_on_grid="1"`: Particles are rendered even if they are on the grid.
*   `is_trail="1"`: This emitter is configured to create a trail effect.
*   `trail_gap="1"`: The spacing between particles in the trail.
*   `airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.22"`: These attributes suggest a subtle influence from airflow, potentially for visual swirling.
*   `emit_cosmetic_particles="1"`: Emits particles that are purely for visual effect.
*   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: Particles are emitted continuously with no delay between emissions.
*   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime approaches zero.
*   `is_emitting="1"`: The emitter is active and will produce particles.

#### LifetimeComponent

Defines the overall lifespan of the entity that spawns these particles.

*   `lifetime="200"`: The base lifespan of the entity.
*   `randomize_lifetime.min="-125"`, `randomize_lifetime.max="75"`: Adds randomness to the entity's lifespan.

#### LuaComponent

Integrates custom Lua scripting for more complex behavior.

*   `script_source_file="data/scripts/particles/swirl_movement.lua"`: This points to an external Lua script that dictates the swirling motion of the particles.
*   `execute_every_n_frame="1"`: The Lua script runs every frame, allowing for dynamic and responsive particle movement.

This configuration results in a particle effect that rapidly emits small, red sparks with a high initial velocity, creating a fast, swirling trail that fades over its short lifetime, driven by a dedicated Lua script for its unique movement pattern.