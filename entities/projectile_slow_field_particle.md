---
title: Projectile Slow Field Particle
category: entities
---

# Projectile Slow Field Particle

This entity defines the visual particle effect for a projectile that creates a slow-down field.

## Key Components

### InheritTransformComponent
This component allows the particle effect to inherit the transform (position, rotation, scale) from its parent entity.

*   **use_root_parent**: `1` - Indicates that the transform should be inherited from the root parent.

### ParticleEmitterComponent
This component is responsible for generating and managing the visual particles.

*   **emitted_material_name**: `spark_purple` - The material used for the emitted particles.
*   **lifetime_min**: `0.06` - Minimum lifetime of each particle in seconds.
*   **lifetime_max**: `0.12` - Maximum lifetime of each particle in seconds.
*   **count_min**: `50` - Minimum number of particles emitted per emission cycle.
*   **count_max**: `70` - Maximum number of particles emitted per emission cycle.
*   **render_on_grid**: `1` - Ensures the particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles will fade out as their lifetime decreases.
*   **area_circle_radius.min**: `72` - Minimum radius of the circular emission area.
*   **area_circle_radius.max**: `72` - Maximum radius of the circular emission area.
*   **airflow_force**: `0.3` - The force applied to particles by airflow.
*   **airflow_time**: `0.01` - The duration for which airflow affects particles.
*   **airflow_scale**: `0.05` - The scaling factor for airflow effects.
*   **emit_cosmetic_particles**: `1` - Enables the emission of cosmetic particles.
*   **is_emitting**: `1` - The particle emitter is active and will emit particles.