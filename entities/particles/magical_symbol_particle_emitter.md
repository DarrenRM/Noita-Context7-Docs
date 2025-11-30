---
title: Magical Symbol Particle Emitter
category: entities/particles
---

# Magical Symbol Particle Emitter

This entity defines a particle emitter that creates magical symbol-like particles.

## ParticleEmitterComponent

This component controls the emission of particles.

### Key Attributes:

*   `emitted_material_name`: Specifies the material of the emitted particles. In this case, it's `"spark_red"`.
*   `gravity.y`: The vertical gravity applied to the particles. Set to `"0.0"` for no gravity.
*   `lifetime_min`, `lifetime_max`: The minimum and maximum lifetime of individual particles in seconds.
*   `count_min`, `count_max`: The minimum and maximum number of particles emitted per emission.
*   `render_on_grid`: Whether the particles should be rendered on the game grid.
*   `fade_based_on_lifetime`: If set to `1`, particles will fade out as their lifetime decreases.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes control an airflow effect applied to the particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the frame interval between particle emissions.
*   `emit_cosmetic_particles`: If set to `1`, particles are considered cosmetic.
*   `image_animation_file`: The path to the image file used for animating the particles.
*   `image_animation_speed`: The speed of the image animation.
*   `image_animation_loop`: Whether the image animation should loop.
*   `is_emitting`: If set to `1`, the emitter is active.

## LifetimeComponent

This component defines the overall lifetime of the entity itself.

### Key Attributes:

*   `lifetime`: The total lifetime of the entity in seconds.