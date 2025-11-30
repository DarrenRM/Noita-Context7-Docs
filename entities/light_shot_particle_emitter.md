---
title: Light Shot Particle Emitter
category: entities
---

# Light Shot Particle Emitter

This document describes the `light_shot.xml` entity, which defines the particle effects for a "light shot" in Noita. It primarily utilizes the `ParticleEmitterComponent` to generate visual sparks.

## ParticleEmitterComponent

This component is responsible for emitting particles.

### Key Attributes:

*   **`emitted_material_name`**: Specifies the material of the particles to be emitted.
    *   Value: `"spark_blue"`
*   **`offset.x`, `offset.y`**: Defines the base offset of the emitter from its parent entity.
    *   Values: `0`, `0`
*   **`x_pos_offset_min`, `x_pos_offset_max`**: Controls the horizontal spread of emitted particles.
    *   Values: `-1`, `1`
*   **`y_pos_offset_min`, `y_pos_offset_max`**: Controls the vertical spread of emitted particles.
    *   Values: `-1`, `1`
*   **`gravity.y`**: The gravitational pull affecting the particles.
    *   Value: `0` (No vertical gravity)
*   **`x_vel_min`, `x_vel_max`**: Minimum and maximum horizontal velocity of emitted particles.
    *   Values: `-2`, `2`
*   **`y_vel_min`, `y_vel_max`**: Minimum and maximum vertical velocity of emitted particles.
    *   Values: `-2`, `2`
*   **`count_min`, `count_max`**: The range for the number of particles emitted per emission cycle.
    *   Values: `2`, `4`
*   **`is_trail`**: Determines if the particles should leave a trail.
    *   Value: `1` (Yes, it's a trail)
*   **`trail_gap`**: The spacing between trail segments.
    *   Value: `1.0`
*   **`fade_based_on_lifetime`**: If particles should fade out as their lifetime decreases.
    *   Value: `1` (Yes, fade based on lifetime)
*   **`lifetime_min`, `lifetime_max`**: The minimum and maximum lifetime of individual particles in seconds.
    *   Values: `0.8`, `2.0`
*   **`airflow_force`**: The strength of airflow affecting particles.
    *   Value: `1.5`
*   **`airflow_time`**: The duration airflow affects particles.
    *   Value: `0.401`
*   **`airflow_scale`**: The scaling factor for airflow.
    *   Value: `0.05`
*   **`create_real_particles`**: Whether to create actual game physics particles.
    *   Value: `0` (No, these are cosmetic)
*   **`emit_cosmetic_particles`**: Whether to emit cosmetic particles.
    *   Value: `1` (Yes, emit cosmetic particles)
*   **`render_on_grid`**: Whether particles should be rendered on the game grid.
    *   Value: `1`
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The minimum and maximum frames between particle emissions.
    *   Values: `1`, `2`
*   **`is_emitting`**: Whether the emitter is currently active.
    *   Value: `1` (Yes, it is emitting)