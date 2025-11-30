---
title: Death Particle Emitter
category: entities
---

# Death Particle Emitter

This entity defines the visual and behavioral properties of particles emitted when certain entities die in Noita. It utilizes a `SpriteParticleEmitterComponent` to manage the particle generation and a `LightComponent` to add a subtle glow.

## SpriteParticleEmitterComponent

This component controls the emission of sprite-based particles.

### Key Attributes:

*   **`sprite_file`**: Specifies the XML file defining the appearance of the individual particles. In this case, it's `data/particles/skull.xml`.
*   **`lifetime`**: The duration each particle exists. Set to `0`, suggesting it might be managed by other components or the sprite itself.
*   **`color.a`**: The initial alpha (transparency) of the particles. `1` means fully opaque.
*   **`color_change.a`**: The rate at which the alpha changes over the particle's lifetime. `-0.5` indicates a gradual fade-out.
*   **`gravity.y`**: The gravitational pull affecting the particles. `10` means they will fall downwards.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the timing between particle emissions, creating a slightly varied burst effect.
*   **`count_min` / `count_max`**: Determines the number of particles emitted per burst. Here, it's always `1`.
*   **`randomize_rotation.min` / `randomize_rotation.max`**: Introduces random rotation to each emitted particle.
*   **`randomize_position.min_x` / `randomize_position.max_x` / `randomize_position.min_y` / `randomize_position.max_y`**: Defines a rectangular area around the emitter where particles can spawn, adding spatial variation.
*   **`randomize_velocity.min_x` / `randomize_velocity.max_x` / `randomize_velocity.min_y` / `randomize_velocity.max_y`**: Assigns a random initial velocity to each particle within a specified range, contributing to their movement.

## LightComponent

This component adds a light source to the entity.

### Key Attributes:

*   **`_enabled`**: Whether the light component is active. `1` means it is enabled.
*   **`radius`**: The range of the light. `60` units.
*   **`r`, `g`, `b`**: The RGB color values of the light. Here, it's a dark blue (`0`, `40`, `80`).