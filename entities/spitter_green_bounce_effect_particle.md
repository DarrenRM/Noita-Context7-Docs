---
title: Spitter Green Bounce Effect Particle
category: entities
---

# Spitter Green Bounce Effect Particle

This entity defines the particle effect that occurs when a "spitter_green" material bounces. It's a simple particle emitter that generates small, green sparks.

## Key Components

### LifetimeComponent

*   **lifetime**: `3` - The total duration this particle effect will exist in seconds.

### ParticleEmitterComponent

This component controls the generation and properties of the emitted particles.

*   **emitted_material_name**: `spark_green` - The material used for the particles being emitted.
*   **gravity.y**: `0.0` - The particles have no vertical gravity applied.
*   **lifetime_min**: `0.05` - The minimum lifetime of each individual particle in seconds.
*   **lifetime_max**: `0.2` - The maximum lifetime of each individual particle in seconds.
*   **x_pos_offset_min/max**: `-2` to `2` - The horizontal offset from the emitter's origin for particle spawn.
*   **y_pos_offset_min/max**: `-2` to `2` - The vertical offset from the emitter's origin for particle spawn.
*   **x_vel_min/max**: `-100` to `0` - The minimum and maximum horizontal velocity for emitted particles.
*   **y_vel_min/max**: `-100` to `100` - The minimum and maximum vertical velocity for emitted particles.
*   **count_min/max**: `14` to `25` - The number of particles emitted per emission cycle.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **emission_interval_min_frames/max_frames**: `1` to `1` - Particles are emitted every frame, creating a continuous stream.
*   **emit_cosmetic_particles**: `1` - This emitter is intended for cosmetic effects.
*   **is_emitting**: `1` - The emitter is active and will produce particles.