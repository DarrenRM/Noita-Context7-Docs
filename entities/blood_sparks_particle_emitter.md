---
title: Blood Sparks Particle Emitter
category: entities
---

# Blood Sparks Particle Emitter

This document describes the configuration for a particle emitter that generates "blood sparks" in Noita.

## ParticleEmitterComponent

This component defines the behavior and properties of the particle emitter.

### Key Attributes:

*   **`emitted_material_name`**: `blood`
    *   Specifies the material of the particles being emitted.
*   **`offset.x`, `offset.y`**: `0`
    *   The base offset from the entity's position where particles are emitted.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-1`, `1`
    *   Defines the minimum and maximum horizontal offset for particle spawn positions.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-1`, `1`
    *   Defines the minimum and maximum vertical offset for particle spawn positions.
*   **`gravity.y`**: `0`
    *   The gravitational pull applied to the particles along the Y-axis. `0` means no gravity.
*   **`x_vel_min`, `x_vel_max`**: `-2`, `2`
    *   The minimum and maximum horizontal velocity applied to emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-2`, `2`
    *   The minimum and maximum vertical velocity applied to emitted particles.
*   **`count_min`, `count_max`**: `1`, `2`
    *   The range for the number of particles emitted per emission event.
*   **`is_trail`**: `1`
    *   Indicates whether the particles should leave a trail. `1` means yes.
*   **`trail_gap`**: `0.7`
    *   The spacing between segments of the particle trail.
*   **`fade_based_on_lifetime`**: `1`
    *   Enables fading of particles as their lifetime progresses. `1` means yes.
*   **`lifetime_min`, `lifetime_max`**: `0.8`, `2.0`
    *   The minimum and maximum duration (in seconds) each particle will exist.
*   **`airflow_force`**: `1.5`
    *   The strength of airflow affecting the particles.
*   **`airflow_time`**: `0.401`
    *   The duration (in seconds) for which airflow affects the particles.
*   **`airflow_scale`**: `0.05`
    *   A scaling factor for the airflow effect.
*   **`create_real_particles`**: `0`
    *   Whether to create actual game entities for these particles. `0` means no.
*   **`emit_cosmetic_particles`**: `1`
    *   Whether to emit particles primarily for visual effect. `1` means yes.
*   **`render_on_grid`**: `1`
    *   Indicates if the particles should be rendered on the game grid. `1` means yes.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`, `2`
    *   The minimum and maximum number of frames between particle emission events.
*   **`is_emitting`**: `1`
    *   Enables or disables the particle emitter. `1` means it is active.