---
title: Tiny Ghost Poof Particle Emitter
category: entities
---

# Tiny Ghost Poof Particle Emitter

This entity defines a particle effect that creates a "tiny ghost poof" visual. It's primarily controlled by a `ParticleEmitterComponent`.

## ParticleEmitterComponent

This component manages the emission of particles.

### Key Attributes:

*   **`emitted_material_name`**: `steam` - The material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity, meaning they won't fall.
*   **`lifetime_min`**: `2` - Minimum lifetime of each emitted particle in seconds.
*   **`lifetime_max`**: `5` - Maximum lifetime of each emitted particle in seconds.
*   **`count_min`**: `1` - Minimum number of particles emitted per emission event.
*   **`count_max`**: `2` - Maximum number of particles emitted per emission event.
*   **`x_pos_offset_min`**: `-2` - Minimum horizontal offset from the emitter's position.
*   **`x_pos_offset_max`**: `2` - Maximum horizontal offset from the emitter's position.
*   **`y_pos_offset_min`**: `-4` - Minimum vertical offset from the emitter's position.
*   **`y_pos_offset_max`**: `3` - Maximum vertical offset from the emitter's position.
*   **`render_on_grid`**: `1` - Particles will be rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles will fade out as their lifetime decreases.
*   **`cosmetic_force_create`**: `0` - This is not a cosmetic-only particle effect.
*   **`airflow_force`**: `0.451` - The strength of airflow affecting the particles.
*   **`airflow_time`**: `1.01` - How long airflow affects the particles.
*   **`airflow_scale`**: `0.25` - The scale of the airflow effect.
*   **`emission_interval_min_frames`**: `1` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `1` - Maximum frames between particle emissions.
*   **`emit_cosmetic_particles`**: `1` - This emitter can emit cosmetic particles.
*   **`is_emitting`**: `1` - The emitter is active and will emit particles.

## LifetimeComponent

This component defines the overall lifetime of the entity itself.

### Key Attributes:

*   **`lifetime`**: `20` - The entity will exist for 20 seconds before being removed.