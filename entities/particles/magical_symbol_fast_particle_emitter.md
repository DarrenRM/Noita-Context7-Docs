---
title: Magical Symbol Fast Particle Emitter
category: entities/particles
---

# Magical Symbol Fast Particle Emitter

This entity defines a particle emitter that creates fast-moving magical symbols.

## ParticleEmitterComponent

This component controls the emission of particles.

### Key Attributes:

*   **`emitted_material_name`**: `spark_red` - The material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity.
*   **`lifetime_min`**: `2` - Minimum lifetime of emitted particles in seconds.
*   **`lifetime_max`**: `5` - Maximum lifetime of emitted particles in seconds.
*   **`count_min`**: `4` - Minimum number of particles emitted per burst.
*   **`count_max`**: `4` - Maximum number of particles emitted per burst.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`airflow_force`**: `0.251` - The force applied by airflow to particles.
*   **`emission_interval_min_frames`**: `1` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `1` - Maximum frames between particle emissions.
*   **`image_animation_file`**: `data/particles/image_emitters/animated_emitter_large.png` - The image file used for particle animation.
*   **`image_animation_speed`**: `3` - The speed of the image animation.
*   **`image_animation_loop`**: `0` - The animation does not loop.
*   **`is_emitting`**: `1` - The emitter is active.

## LifetimeComponent

This component defines the overall lifetime of the entity itself.

### Key Attributes:

*   **`lifetime`**: `260` - The entity will exist for 260 seconds.