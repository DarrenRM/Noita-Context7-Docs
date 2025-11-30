---
title: Electrified Ragdoll Part
category: entities
---

# Electrified Ragdoll Part

This entity defines a component that adds an electrified visual effect to a ragdoll part. It primarily uses particle emitters to simulate sparks and electrical discharges.

## Key Components

### LifetimeComponent

*   **lifetime**: The duration in frames for which this electrified effect will persist.

### SpriteParticleEmitterComponent

This component controls the emission of sprite-based particles, likely for a more distinct spark effect.

*   **sprite_file**: Path to the particle sprite definition (e.g., `data/particles/spark_electric.xml`).
*   **delay**: Delay in frames before particle emission starts.
*   **lifetime**: Lifetime of individual particles in frames.
*   **color.r, color.g, color.b, color.a**: Initial color of the particles.
*   **color_change.r, color_change.g, color_change.b, color_change.a**: How the color changes over the particle's lifetime.
*   **gravity.y**: The gravitational pull on the particles.
*   **emission_interval_min_frames, emission_interval_max_frames**: The range for how often new particles are emitted.
*   **count_min, count_max**: The number of particles emitted per interval.
*   **randomize_rotation.min, randomize_rotation.max**: Range for randomizing the initial rotation of particles.
*   **randomize_velocity.min\_x, randomize_velocity.max\_x, randomize_velocity.min\_y, randomize_velocity.max\_y**: Range for randomizing the initial velocity of particles.

### ParticleEmitterComponent

This component emits simpler, material-based particles, likely for a more general electrical discharge effect.

*   **emitted_material_name**: The name of the material to be used for emitted particles (e.g., `spark_blue`).
*   **offset.x, offset.y**: Offset from the entity's origin for particle emission.
*   **x\_pos\_offset\_min, x\_pos\_offset\_max, y\_pos\_offset\_min, y\_pos\_offset\_max**: Range for randomizing the position of emitted particles relative to the offset.
*   **x\_vel\_min, x\_vel\_max, y\_vel\_min, y\_vel\_max**: Range for the initial velocity of emitted particles.
*   **count\_min, count\_max**: The number of particles emitted per interval.
*   **lifetime\_min, lifetime\_max**: The range for the lifetime of individual particles in seconds.
*   **create\_real\_particles**: Whether to create actual physics-enabled particles.
*   **emit\_cosmetic\_particles**: Whether to emit particles that are purely visual.
*   **emission\_interval\_min\_frames, emission\_interval\_max\_frames**: The range for how often new particles are emitted.
*   **is\_emitting**: Whether the emitter is currently active.