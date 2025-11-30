---
title: Teleport Hourglass Return FX
category: entities
---

# Teleport Hourglass Return FX

This entity defines the visual effects associated with the return teleportation of the Hourglass building in Noita. It primarily uses a `ParticleEmitterComponent` to generate purple sparks.

## ParticleEmitterComponent

This component controls the emission of particles.

### Key Attributes:

*   **`emitted_material_name`**: `spark_purple` - Specifies the material used for the emitted particles.
*   **`offset.y`**: `-90` - The vertical offset of the particle emitter relative to the entity's origin.
*   **`y_vel_min` / `y_vel_max`**: `60` - The minimum and maximum vertical velocity of the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `10` to `20` - The duration (in frames) each particle will exist.
*   **`count_min` / `count_max`**: `1` - The number of particles emitted per emission event.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` - The particles are emitted continuously with no delay between emissions.
*   **`is_emitting`**: `1` - Enables the particle emission.
*   **`emit_cosmetic_particles`**: `1` - Indicates these are cosmetic particles, not affecting gameplay mechanics.
*   **`airflow_force`**: `0.02` - A slight force applied to particles due to airflow.
*   **`airflow_time`**: `1.01` - The duration airflow affects particles.
*   **`airflow_scale`**: `0.03` - The intensity of the airflow effect.