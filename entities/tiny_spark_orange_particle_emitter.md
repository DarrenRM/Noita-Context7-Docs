---
title: Tiny Spark Orange Particle Emitter
category: entities
---

# Tiny Spark Orange Particle Emitter

This document describes the configuration for a particle emitter that generates small, orange sparks in Noita. This is useful for AI-assisted modding to understand and modify particle effects.

## ParticleEmitterComponent

This is the core component responsible for emitting particles.

### Key Attributes:

*   **`emitted_material_name`**: `spark` - Specifies the material of the particles being emitted.
*   **`offset.x`, `offset.y`**: `0` - The base offset from the entity's position where particles are emitted.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-1` to `1` - The range of random horizontal offset for emitted particles.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-1` to `1` - The range of random vertical offset for emitted particles.
*   **`gravity.y`**: `0` - The vertical gravity applied to the particles. `0` means no gravity.
*   **`x_vel_min`, `x_vel_max`**: `-2` to `2` - The range of horizontal velocity for emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-2` to `2` - The range of vertical velocity for emitted particles.
*   **`count_min`, `count_max`**: `1` to `3` - The minimum and maximum number of particles emitted per emission.
*   **`is_trail`**: `1` - Indicates that the particles should leave a trail.
*   **`trail_gap`**: `1` - The spacing between segments of the particle trail.
*   **`fade_based_on_lifetime`**: `1` - Particles will fade out as their lifetime progresses.
*   **`lifetime_min`, `lifetime_max`**: `0.8` to `3.0` - The minimum and maximum lifetime of each particle in seconds.
*   **`airflow_force`**: `1.5` - The strength of airflow affecting the particles.
*   **`airflow_time`**: `0.401` - The duration for which airflow affects the particles.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow's influence.
*   **`create_real_particles`**: `0` - Whether to create actual game entities for these particles. `0` means cosmetic only.
*   **`emit_cosmetic_particles`**: `1` - Whether to emit particles that are purely visual.
*   **`render_on_grid`**: `1` - Particles will be rendered on the game grid.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1` to `2` - The minimum and maximum number of frames between particle emissions.
*   **`is_emitting`**: `1` - Enables the particle emitter.