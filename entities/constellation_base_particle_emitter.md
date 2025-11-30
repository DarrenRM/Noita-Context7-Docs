---
title: Constellation Base Particle Emitter
category: entities
---

# Constellation Base Particle Emitter

This entity defines a basic particle emitter used for introductory visual effects, likely for constellations or similar celestial elements.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles.

*   **`emitted_material_name`**: `spark_white_bright` - Specifies the material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.0` / `0.9` - Particles have a very short lifespan.
*   **`count_min` / `count_max`**: `1` / `1` - Emits a single particle per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime ends.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `0` / `0` - Particles are emitted from a single point.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `0` / `1` - Particles are emitted very frequently, almost continuously.
*   **`emission_chance`**: `30` - There's a 30% chance of emitting particles on each interval.
*   **`emit_cosmetic_particles`**: `1` - Emits particles that are purely visual.
*   **`image_animation_file`**: `data/entities/intro/00.png` - Uses a specific animation file for particle appearance.
*   **`image_animation_speed`**: `5` - Controls the speed of the particle image animation.
*   **`image_animation_loop`**: `1` - The particle animation will loop.
*   **`is_emitting`**: `1` - The emitter is active.
*   **`render_back`**: `1` - Particles are rendered behind other elements.

### LifetimeComponent

This component defines the lifespan of the entity itself.

*   **`lifetime`**: `60` - The entity will exist for 60 seconds.