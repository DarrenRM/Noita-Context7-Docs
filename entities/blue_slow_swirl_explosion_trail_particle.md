---
title: Blue Slow Swirl Explosion Trail Particle
category: entities
---

# Blue Slow Swirl Explosion Trail Particle

This document describes the configuration for a specific particle effect in Noita, designed to create a slow, swirling blue trail following an explosion.

## Entity Configuration

The core of this particle effect is defined within an `<Entity>` tag.

### Key Components and Attributes

This particle utilizes several components to achieve its visual and behavioral characteristics.

#### VelocityComponent

Controls the movement and physics of the particle.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
*   `air_friction="2"`: Applies a moderate amount of air friction, slowing the particle over time.
*   `updates_velocity="1"`: Enables the component to actively update the particle's velocity.

#### SimplePhysicsComponent

A basic physics component, likely used in conjunction with other components for movement.

#### SetStartVelocityComponent

Determines the initial velocity of the emitted particles.

*   `randomize_speed.min="50"`: The minimum initial speed of the particle.
*   `randomize_speed.max="200"`: The maximum initial speed of the particle.
*   `randomize_angle.min="0"`: The minimum initial angle of the particle's velocity.
*   `randomize_angle.max="6.283185"`: The maximum initial angle (approximately 2π radians or 360 degrees), allowing for omnidirectional initial movement.

#### ParticleEmitterComponent

This is the primary component responsible for generating and managing the particles.

*   `emitted_material_name="plasma_fading"`: Specifies the material of the particles being emitted. "plasma\_fading" suggests a material that gradually disappears.
*   `delay_frames="2"`: A short delay before the emitter starts.
*   `gravity.y="0"`: The emitted particles are not affected by gravity.
*   `friction="10"`: A high friction value applied to the emitted particles, causing them to slow down quickly.
*   `count_min="0"` / `count_max="1"`: Emits either 0 or 1 particle per emission cycle.
*   `lifetime_min="0.5"` / `lifetime_max="2.5"`: The lifespan of each emitted particle, ranging from 0.5 to 2.5 seconds.
*   `emit_real_particles="0"`: Indicates that these are not "real" particles in the game's physics simulation, but rather visual effects.
*   `is_trail="1"`: Crucially, this marks the emitter as generating a trail effect.
*   `trail_gap="1"`: The spacing between particles in the trail.
*   `airflow_force="0.3"`: Applies a subtle force related to airflow.
*   `airflow_time="0.01"`: The duration for which airflow affects the particle.
*   `airflow_scale="0.22"`: The intensity of the airflow effect.
*   `emit_cosmetic_particles="1"`: Ensures these are treated as cosmetic visual effects.
*   `emission_interval_min_frames="1"` / `emission_interval_max_frames="1"`: Particles are emitted every frame, creating a continuous trail.
*   `fade_based_on_lifetime="1"`: The particle's visibility fades as its lifetime decreases.
*   `is_emitting="1"`: The emitter is active and will produce particles.

#### LifetimeComponent

Defines the overall lifespan of the entity that spawns these particles.

*   `lifetime="100"`: The base lifespan of the entity.
*   `randomize_lifetime.min="-75"` / `randomize_lifetime.max="35"`: Introduces variability to the entity's lifespan.

#### LuaComponent

Integrates custom Lua scripting for more complex behavior.

*   `script_source_file="data/scripts/particles/swirl_movement.lua"`: This component executes a Lua script named `swirl_movement.lua`. This script is responsible for the characteristic swirling motion of the particles.
*   `execute_every_n_frame="1"`: The Lua script is executed every frame, allowing for dynamic and continuous adjustments to particle behavior.

### Summary

This particle effect is designed to be a visual trail. It emits particles with a fading material, a high friction to slow them down, and a specific Lua script (`swirl_movement.lua`) to give them a swirling motion. The `is_trail="1"` attribute is key to its function as a trail effect. The `SetStartVelocityComponent` provides initial direction and speed, while the `ParticleEmitterComponent` controls the emission rate, particle lifespan, and trail properties. The `LuaComponent` is essential for the unique swirling behavior.