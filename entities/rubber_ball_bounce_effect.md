---
title: Rubber Ball Bounce Effect
category: entities
---

# Rubber Ball Bounce Effect

This entity defines the visual effect that occurs when a rubber ball bounces in Noita. It primarily consists of a particle emitter that spawns small, short-lived particles.

## Key Components

### LifetimeComponent

*   **lifetime**: `4` - The total duration this effect will exist in seconds.

### ParticleEmitterComponent

This component controls the emission of particles that create the bounce visual.

*   **emitted_material_name**: `spark_green` - The material of the particles being emitted. In this case, green sparks.
*   **lifetime_min**: `0.05` - The minimum lifetime of each emitted particle in seconds.
*   **lifetime_max**: `0.1` - The maximum lifetime of each emitted particle in seconds.
*   **x_pos_offset_min/max**: `-2` to `2` - The horizontal spread of particle emission around the origin.
*   **y_pos_offset_min/max**: `-2` to `2` - The vertical spread of particle emission around the origin.
*   **x_vel_min/max**: `-100` to `0` - The horizontal velocity range for emitted particles. Particles will generally move leftwards or stay still horizontally.
*   **y_vel_min/max**: `-50` to `50` - The vertical velocity range for emitted particles.
*   **gravity.y**: `0.0` - Particles are not affected by gravity.
*   **count_min/max**: `4` to `10` - The number of particles emitted per emission event.
*   **emission_interval_min_frames/max_frames**: `1` to `1` - Particles are emitted every frame, creating a continuous stream while the emitter is active.
*   **emit_cosmetic_particles**: `1` - Indicates that these are cosmetic particles, not affecting gameplay mechanics directly.
*   **is_emitting**: `1` - The particle emitter is active.