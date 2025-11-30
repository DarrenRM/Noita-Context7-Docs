---
title: Spiral Shot Particle
category: entities
---

# Spiral Shot Particle

This entity defines the visual particles associated with a "spiral shot" effect in Noita. It utilizes two identical `ParticleEmitterComponent` instances to generate fading plasma particles.

## Key Components

### ParticleEmitterComponent

This component is responsible for emitting particles. The configuration is duplicated, suggesting a potential for subtle variations or simply redundancy.

*   **`emitted_material_name`**: `plasma_fading` - Specifies the material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity in the Y-axis.
*   **`lifetime_min`**: `0.1` - Minimum lifetime of each particle in seconds.
*   **`lifetime_max`**: `1.5` - Maximum lifetime of each particle in seconds.
*   **`count_min`**: `1` - Minimum number of particles emitted per emission.
*   **`count_max`**: `1` - Maximum number of particles emitted per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime progresses.
*   **`cosmetic_force_create`**: `0` - Particles are not forced to be created cosmetically.
*   **`airflow_force`**: `0.3` - The strength of airflow affecting the particles.
*   **`airflow_time`**: `0.01` - The duration airflow is applied.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow.
*   **`emission_interval_min_frames`**: `0` - Minimum frames between emissions.
*   **`emission_interval_max_frames`**: `0` - Maximum frames between emissions.
*   **`emit_cosmetic_particles`**: `1` - Cosmetic particles are emitted.
*   **`is_emitting`**: `1` - The emitter is active.

### LifetimeComponent

*   **`lifetime`**: `10` - The total lifetime of the entity itself in seconds.