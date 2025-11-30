---
title: Shop Effect Particle Emitter
category: entities
---

# Shop Effect Particle Emitter

This entity defines a particle emitter that creates visual effects commonly seen in shops, likely for decorative purposes.

## ParticleEmitterComponent

This component controls the emission of particles.

### Key Attributes:

*   **emitted_material_name**: `spark_yellow` - The material of the particles being emitted.
*   **gravity.y**: `0.0` - Particles are not affected by gravity.
*   **lifetime_min**: `8` - Minimum lifetime of each emitted particle in seconds.
*   **lifetime_max**: `15` - Maximum lifetime of each emitted particle in seconds.
*   **count_min**: `15` - Minimum number of particles emitted per emission.
*   **count_max**: `15` - Maximum number of particles emitted per emission.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **airflow_force**: `1.551` - The force applied to particles by airflow.
*   **airflow_time**: `1.01` - The duration airflow affects particles.
*   **airflow_scale**: `0.05` - The scale of the airflow effect.
*   **emission_interval_min_frames**: `1` - Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `1` - Maximum frames between particle emissions.
*   **emit_cosmetic_particles**: `1` - Emits cosmetic particles.
*   **image_animation_file**: `data/particles/image_emitters/shop_effect.png` - The image file used for particle animation.
*   **image_animation_speed**: `15` - The speed of the image animation.
*   **image_animation_loop**: `0` - The animation does not loop.
*   **is_emitting**: `1` - The emitter is active.

## LifetimeComponent

This component defines the overall lifetime of the entity itself.

### Key Attributes:

*   **lifetime**: `260` - The total lifetime of the entity in seconds.