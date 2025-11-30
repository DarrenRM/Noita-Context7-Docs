---
title: Tiny Green Spark Particle Emitter
category: entities
---

# Tiny Green Spark Particle Emitter

This document describes the configuration for a particle emitter that generates small, green sparks in Noita. This is useful for AI-assisted modding to understand and modify particle effects.

## ParticleEmitterComponent

This is the core component responsible for emitting particles.

### Key Attributes:

*   **`emitted_material_name`**: `spark_green` - Specifies the material/type of particle to be emitted.
*   **`offset.x`, `offset.y`**: `0` - The base offset from the entity's position where particles are emitted.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-1`, `1` - Defines the range for random horizontal position offset for each emitted particle.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-1`, `1` - Defines the range for random vertical position offset for each emitted particle.
*   **`gravity.y`**: `0` - The vertical gravity applied to the emitted particles. `0` means no gravity.
*   **`x_vel_min`, `x_vel_max`**: `-2`, `2` - The minimum and maximum horizontal velocity applied to emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-2`, `2` - The minimum and maximum vertical velocity applied to emitted particles.
*   **`count_min`, `count_max`**: `1`, `3` - The range for the number of particles emitted per emission event.
*   **`is_trail`**: `1` - Indicates that these particles should leave a trail.
*   **`trail_gap`**: `1` - The spacing between segments of the particle trail.
*   **`fade_based_on_lifetime`**: `1` - Particles will fade out as their lifetime approaches zero.
*   **`lifetime_min`, `lifetime_max`**: `0.8`, `2.0` - The minimum and maximum lifetime in seconds for each emitted particle.
*   **`airflow_force`**: `1.5` - The strength of airflow affecting the particles.
*   **`airflow_time`**: `0.401` - The duration for which airflow affects the particles.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow's influence.
*   **`create_real_particles`**: `0` - Whether to create actual game entities for these particles (0 means cosmetic only).
*   **`emit_cosmetic_particles`**: `1` - Whether to emit particles that are purely visual.
*   **`render_on_grid`**: `1` - Whether the particles should be rendered on the game grid.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`, `2` - The minimum and maximum number of frames between emission events.
*   **`is_emitting`**: `1` - Whether the emitter is currently active.