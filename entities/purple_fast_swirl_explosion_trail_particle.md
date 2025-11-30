---
title: Purple Fast Swirl Explosion Trail Particle
category: entities
---

# Purple Fast Swirl Explosion Trail Particle

This entity defines a particle that creates a fast-swirling purple trail effect, often used in explosions.

## Key Components and Attributes

### VelocityComponent
Controls the particle's movement.

*   `gravity_y="0"`: The particle is not affected by gravity.
*   `air_friction="2"`: Applies a moderate amount of air friction.
*   `updates_velocity="1"`: Enables velocity updates.

### SetStartVelocityComponent
Determines the initial speed and direction of the particle.

*   `randomize_speed.min="450"`: Minimum initial speed.
*   `randomize_speed.max="600"`: Maximum initial speed.
*   `randomize_angle.min="0"`: Minimum initial angle (in radians).
*   `randomize_angle.max="6.283185"`: Maximum initial angle (full circle).

### ParticleEmitterComponent
Manages the emission of particles that form the trail.

*   `emitted_material_name="spark_purple_bright"`: The material of the particles being emitted.
*   `delay_frames="2"`: A short delay before emitting the first particle.
*   `gravity.y="0"`: Emitted particles are not affected by gravity.
*   `friction="10"`: High friction applied to emitted particles.
*   `count_min="0"` / `count_max="1"`: Emits a very small number of particles per emission.
*   `lifetime_min="0.5"` / `lifetime_max="2.5"`: The lifespan of individual emitted particles.
*   `emit_real_particles="0"`: This is a cosmetic particle emitter.
*   `is_trail="1"`: Indicates this emitter is designed to create a trail.
*   `trail_gap="1"`: The spacing between particles in the trail.
*   `airflow_force="0.3"`: Applies a slight force from airflow.
*   `airflow_time="0.01"`: The duration of the airflow effect.
*   `airflow_scale="0.22"`: The intensity of the airflow effect.
*   `emit_cosmetic_particles="1"`: Emits particles that are purely visual.
*   `emission_interval_min_frames="1"` / `emission_interval_max_frames="1"`: Particles are emitted every frame.
*   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime ends.
*   `is_emitting="1"`: The emitter is active.

### LifetimeComponent
Determines the lifespan of the entity itself.

*   `lifetime="100"`: Base lifespan of the entity.
*   `randomize_lifetime.min="-75"` / `randomize_lifetime.max="75"`: Random variation in the entity's lifespan.

### LuaComponent
Applies custom Lua scripting for particle behavior.

*   `script_source_file="data/scripts/particles/swirl_movement.lua"`: The script responsible for the swirling motion.
*   `execute_every_n_frame="1"`: The script runs every frame.