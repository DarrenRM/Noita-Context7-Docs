---
title: Boss Alchemist Key Particles Second Alt
category: entities
---

---

# Boss Alchemist Key Particles Second Alt

This entity defines particle effects associated with the Boss Alchemist, specifically for a secondary alternative state. It utilizes two `ParticleEmitterComponent` instances to generate different types of particles.

## Key Components

### InheritTransformComponent

This component is present to inherit transformations, likely for positioning and orientation within the game world.

*   **_tags**: `second,enabled_in_hand,enabled_in_world,item_identified` - Indicates the particle system's state and when it should be active.

### ParticleEmitterComponent (Green Sparks)

This component manages the emission of green sparks.

*   **_tags**: `second,enabled_in_hand,enabled_in_world,item_identified` - Same as above, ensuring consistent activation.
*   **emitted_material_name**: `spark_green` - Specifies the material used for the emitted particles.
*   **gravity.y**: `0.0` - Particles are not affected by vertical gravity.
*   **lifetime_min**: `1.5` - Minimum duration a particle exists.
*   **lifetime_max**: `8.5` - Maximum duration a particle exists.
*   **count_min**: `1` - Minimum number of particles emitted per emission.
*   **count_max**: `2` - Maximum number of particles emitted per emission.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **area_circle_radius.max**: `24` - The maximum radius of the circular emission area.
*   **cosmetic_force_create**: `1` - Ensures particles are created even if not strictly necessary for gameplay.
*   **airflow_force**: `0.5` - Strength of airflow affecting particles.
*   **airflow_time**: `0.01` - Duration airflow affects particles.
*   **airflow_scale**: `0.05` - Scale of airflow effect.
*   **attractor_force**: `3` - Strength of any attractors affecting particles.
*   **emission_interval_min_frames**: `1` - Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `5` - Maximum frames between particle emissions.
*   **emit_cosmetic_particles**: `1` - Emits particles designated as cosmetic.
*   **collide_with_grid**: `0` - Particles do not collide with the game grid.

### ParticleEmitterComponent (White Sparks)

This component manages the emission of white sparks, with similar properties but different parameters for distinct visual behavior.

*   **_tags**: `second,enabled_in_hand,enabled_in_world,item_identified` - Consistent activation tags.
*   **emitted_material_name**: `spark_white` - Specifies the material for white sparks.
*   **gravity.y**: `0.0` - No vertical gravity.
*   **lifetime_min**: `2.5` - Minimum particle lifetime.
*   **lifetime_max**: `13.5` - Maximum particle lifetime.
*   **count_min**: `1` - Minimum particles per emission.
*   **count_max**: `2` - Maximum particles per emission.
*   **render_on_grid**: `1` - Rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Fades based on lifetime.
*   **area_circle_radius.max**: `8` - Smaller emission radius compared to green sparks.
*   **cosmetic_force_create**: `1` - Ensures cosmetic particle creation.
*   **airflow_force**: `0.5` - Airflow strength.
*   **airflow_time**: `0.01` - Airflow duration.
*   **airflow_scale**: `0.05` - Airflow scale.
*   **attractor_force**: `3` - Attractor strength.
*   **emission_interval_min_frames**: `4` - Slower emission interval.
*   **emission_interval_max_frames**: `14` - Slower emission interval.
*   **emit_cosmetic_particles**: `1` - Emits cosmetic particles.
*   **collide_with_grid**: `0` - No collision with the grid.