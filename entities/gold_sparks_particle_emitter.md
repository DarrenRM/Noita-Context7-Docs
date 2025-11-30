---
title: Gold Sparks Particle Emitter
category: entities
---

# Gold Sparks Particle Emitter

This document describes the configuration for a particle emitter that generates "gold sparks" in Noita.

## ParticleEmitterComponent

This component defines the behavior and properties of the particle emitter.

### Key Attributes:

*   **`emitted_material_name`**: `gold`
    *   Specifies the material associated with the emitted particles. In this case, it's gold.
*   **`offset.x`, `offset.y`**: `0`
    *   The base offset from the entity's position where particles are emitted.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-1`, `1`
    *   Defines the minimum and maximum horizontal positional offset for emitted particles.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-1`, `1`
    *   Defines the minimum and maximum vertical positional offset for emitted particles.
*   **`gravity.y`**: `0`
    *   The gravitational pull on the particles in the Y-axis. `0` means no gravity.
*   **`x_vel_min`, `x_vel_max`**: `-2`, `2`
    *   The minimum and maximum horizontal velocity applied to emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-2`, `2`
    *   The minimum and maximum vertical velocity applied to emitted particles.
*   **`count_min`, `count_max`**: `1`, `2`
    *   The range for the number of particles emitted per emission event.
*   **`is_trail`**: `1`
    *   Indicates whether the particles should behave as a trail. `1` means yes.
*   **`trail_gap`**: `0.7`
    *   The spacing between particles when `is_trail` is enabled.
*   **`fade_based_on_lifetime`**: `1`
    *   Enables fading of particles as their lifetime progresses.
*   **`lifetime_min`, `lifetime_max`**: `0.8`, `2.0`
    *   The minimum and maximum lifetime (in seconds) for each emitted particle.
*   **`airflow_force`**: `1.5`
    *   The strength of the airflow effect on particles.
*   **`airflow_time`**: `0.401`
    *   The duration for which airflow affects particles.
*   **`airflow_scale`**: `0.05`
    *   The scaling factor for the airflow effect.
*   **`create_real_particles`**: `0`
    *   Determines if actual game physics particles are created. `0` means no.
*   **`emit_cosmetic_particles`**: `1`
    *   Enables the emission of cosmetic particles (visual effects without physics).
*   **`render_on_grid`**: `1`
    *   Allows particles to be rendered on the game grid.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`, `2`
    *   The minimum and maximum number of frames between particle emission events.
*   **`is_emitting`**: `1`
    *   Enables or disables the particle emitter. `1` means it is active.