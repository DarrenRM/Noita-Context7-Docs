---
title: Charm Particle Emitter
category: entities/particles
---

# Charm Particle Emitter

This document describes the configuration for a particle emitter that generates "charm" particles in Noita. These particles are visually distinct and have associated lighting effects.

## SpriteParticleEmitterComponent

This component defines the behavior and appearance of the particles being emitted.

### Key Attributes:

*   **`sprite_file`**: Specifies the XML file that defines the sprite for the particles. In this case, it points to `data/particles/charm.xml`.
*   **`delay`**: The initial delay before particle emission begins. Set to `0` for immediate emission.
*   **`emissive`**: Controls whether the particles emit light. `1` means they are emissive.
*   **`lifetime`**: The duration in seconds each particle exists before disappearing. Set to `1.5` seconds.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: The initial RGBA color of the particles. Here, it's set to white (`1, 1, 1, 1`).
*   **`color_change.r`, `color_change.g`, `color_change.b`, `color_change.a`**: The change in RGBA color per second. `color_change.a="-1"` indicates the alpha (transparency) decreases over time, causing the particles to fade out.
*   **`gravity.y`**: The gravitational pull on the particles along the Y-axis. Set to `10`.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The minimum and maximum number of frames between particle emissions. This controls the rate of emission.
*   **`count_min`, `count_max`**: The minimum and maximum number of particles emitted per emission event. Here, it's always `1` particle.
*   **`randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`**: Defines a rectangular area around the emitter's origin where particles can spawn. This creates a spread effect.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y`**: Defines a range of random velocities applied to each emitted particle, contributing to their movement.

## LightComponent

This component adds a light source associated with the particles.

### Key Attributes:

*   **`_enabled`**: Whether the light component is active. `1` means enabled.
*   **`radius`**: The radius of the light's influence. Set to `60`.
*   **`r`, `g`, `b`**: The RGB color of the light. Here, it's a dark blue (`0, 40, 80`).