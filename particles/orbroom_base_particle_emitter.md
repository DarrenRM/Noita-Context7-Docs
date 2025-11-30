---
title: Orbroom Base Particle Emitter
category: particles
---

# Orbroom Base Particle Emitter

This document describes the base particle emitter configuration for orbrooms in Noita, focusing on its visual effects.

## ParticleEmitterComponent

This component defines the behavior and appearance of the emitted particles.

### Key Attributes:

*   **`emitted_material_name`**: Specifies the material of the particles being emitted.
    *   `spark_red`: Indicates red sparks.
*   **`lifetime_min` / `lifetime_max`**: The minimum and maximum duration (in seconds) each particle exists.
    *   `0.5` / `1`
*   **`count_min` / `count_max`**: The minimum and maximum number of particles emitted per emission event.
    *   `1` / `1`
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the frequency of particle emissions in frames.
    *   `1` / `1`: Particles are emitted every frame.
*   **`image_animation_file`**: The sprite sheet used for animating the particles.
    *   `data/particles/image_emitters/orbrooms/07.png`
*   **`image_animation_speed`**: The speed at which the particle animation plays.
    *   `5`
*   **`image_animation_loop`**: Whether the particle animation should loop.
    *   `1`: True (loops).
*   **`emit_cosmetic_particles`**: Determines if these are cosmetic particles (non-interactive).
    *   `1`: True.
*   **`render_back`**: Whether the particles should render behind other elements.
    *   `1`: True.

## LifetimeComponent

This component defines the lifetime of the entity itself.

### Key Attributes:

*   **`lifetime`**: The total duration the entity (and its associated emitter) will exist.
    *   `350` (seconds)