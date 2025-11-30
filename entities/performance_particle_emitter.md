---
title: Performance Particle Emitter
category: entities
---

# Performance Particle Emitter

This entity defines a particle emitter designed for performance testing or debugging. It generates a large number of particles with specific properties to observe their behavior and impact on frame rates.

## ParticleEmitterComponent

This is the core component responsible for emitting particles.

### Key Attributes:

*   **`emitted_material_name`**: `plasma_fading_green`
    *   Specifies the material of the particles being emitted.
*   **`offset.x`, `offset.y`**: `0`
    *   The base offset from the emitter's position.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-10` to `10`
    *   Defines the horizontal range for random particle position offsets.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-10` to `10`
    *   Defines the vertical range for random particle position offsets.
*   **`gravity.y`**: `0`
    *   The gravitational pull on the particles in the Y-axis. `0` means no gravity.
*   **`x_vel_min`, `x_vel_max`**: `-3` to `3`
    *   The minimum and maximum horizontal velocity for emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-3` to `3`
    *   The minimum and maximum vertical velocity for emitted particles.
*   **`count_min`, `count_max`**: `1000`
    *   The number of particles to emit per emission cycle.
*   **`lifetime_min`, `lifetime_max`**: `0.2` to `2.0`
    *   The minimum and maximum lifespan of each particle in seconds.
*   **`airflow_force`**: `1.0`
    *   The strength of airflow affecting particles.
*   **`airflow_time`**: `0.401`
    *   The duration airflow affects particles.
*   **`airflow_scale`**: `0.25`
    *   The scaling factor for airflow.
*   **`is_trail`**: `0`
    *   Whether particles should leave trails. `0` means no trails.
*   **`create_real_particles`**: `0`
    *   Whether to create actual game entities for particles. `0` means cosmetic only.
*   **`emit_cosmetic_particles`**: `1`
    *   Whether to emit cosmetic particles. `1` means yes.
*   **`render_on_grid`**: `1`
    *   Whether particles should be rendered on the game grid. `1` means yes.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`
    *   The interval in frames between particle emissions. `1` means continuous emission.
*   **`fade_based_on_lifetime`**: `1`
    *   Whether particles should fade out as their lifetime decreases. `1` means yes.
*   **`is_emitting`**: `1`
    *   Whether the emitter is currently active. `1` means yes.