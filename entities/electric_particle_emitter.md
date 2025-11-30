---
title: Electric Particle Emitter
category: entities
---

# Electric Particle Emitter

This entity defines a particle emitter that generates electric sparks. It's primarily used for visual effects related to electricity.

## SpriteParticleEmitterComponent

This component controls the emission of sprite-based particles.

### Key Attributes:

*   **`sprite_file`**: Specifies the sprite to be used for the particles.
    *   `data/particles/spark_electric.xml`
*   **`lifetime`**: Duration each particle exists.
    *   `0` (This suggests particles might be managed by other systems or have a very short lifespan).
*   **`color`**: Initial color of the particles (RGBA).
    *   `r="1" g="1" b="1" a="1"` (White)
*   **`color_change`**: How the color changes over the particle's lifetime (RGBA).
    *   `r="0" g="0" b="0" a="0"` (No color change)
*   **`velocity`**: Initial velocity of the particles (XY).
    *   `x="0" y="0"`
*   **`gravity`**: Gravity applied to the particles (XY).
    *   `x="0" y="10"` (Slight downward pull)
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the timing between particle emissions.
    *   `min="1" max="3"` (Emits a particle every 1 to 3 frames)
*   **`count_min` / `count_max`**: Number of particles emitted per interval.
    *   `min="1" max="1"` (Emits one particle at a time)
*   **`randomize_rotation`**: Range for randomizing particle rotation.
    *   `min="-3.1415" max="3.1415"` (Full random rotation)
*   **`randomize_position`**: Range for randomizing particle spawn position relative to the emitter.
    *   `min_x="-2" max_x="2"`
    *   `min_y="-2" max_y="2"`

## LightComponent

This component adds a light source to the entity.

### Key Attributes:

*   **`radius`**: The radius of the light's influence.
    *   `60`
*   **`r`**, **`g`**, **`b`**: The RGB color of the light.
    *   `r="0" g="40" b="80"` (A bluish hue)