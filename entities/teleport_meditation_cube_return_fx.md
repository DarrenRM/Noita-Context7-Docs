---
title: Teleport Meditation Cube Return FX
category: entities
---

---

# Teleport Meditation Cube Return FX

This entity defines the visual effects associated with the return animation of the Teleport Meditation Cube. It primarily uses a `ParticleEmitterComponent` to generate purple sparks.

## Entity: `cube_fx`

### Key Components:

*   **`ParticleEmitterComponent`**: This is the core component responsible for generating the visual effects.

    *   **`emitted_material_name`**: `spark_purple` - Specifies the material used for the emitted particles.
    *   **`offset.x`, `offset.y`**: `0` - The particles are emitted from the exact center of the entity.
    *   **`gravity.y`**: `0` - Particles are not affected by gravity.
    *   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: `0` - Particles have no initial velocity, suggesting they are spawned in place.
    *   **`friction`**: `0` - Particles do not lose velocity due to friction.
    *   **`count_min`, `count_max`**: `1` - Exactly one particle is emitted per emission event.
    *   **`lifetime_min`, `lifetime_max`**: `0.35` to `2.55` - The duration each particle exists.
    *   **`emit_real_particles`**: `0` - These are not "real" physics particles, likely for performance.
    *   **`render_on_grid`**: `1` - The particles are rendered on the game grid.
    *   **`is_trail`**: `1` - Particles leave a trail.
    *   **`trail_gap`**: `1` - The gap between segments of the particle trail.
    *   **`emit_cosmetic_particles`**: `1` - These are cosmetic effects, not gameplay-impacting.
    *   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
    *   **`airflow_force`, `airflow_time`, `airflow_scale`**: These attributes (`0.251`, `1.01`, `0.03` respectively) suggest a subtle influence of airflow on the particles, possibly creating a gentle swirling or drifting effect.
    *   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1` - Particles are emitted continuously every frame.
    *   **`is_emitting`**: `1` - The particle emitter is active.