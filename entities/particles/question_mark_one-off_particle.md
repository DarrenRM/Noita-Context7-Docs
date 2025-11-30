---
title: Question Mark One-Off Particle
category: entities/particles
---

# Question Mark One-Off Particle

This entity defines a single-use particle effect that visually resembles a question mark. It's designed to be spawned and then disappear after a short duration.

## Key Components

### Base Entity

The particle inherits its base properties from `data/entities/particles/charm.xml`.

### SpriteParticleEmitterComponent

This component controls the visual emission of the particle.

*   **`sprite_file`**: Specifies the sprite to be used for the particle.
    *   `data/particles/questionmark.xml`
*   **`emission_interval_min_frames`**: The minimum number of frames between particle emissions.
    *   `5`
*   **`emission_interval_max_frames`**: The maximum number of frames between particle emissions.
    *   `15`
*   **`randomize_position_inside_hitbox`**: Whether to randomize the particle's spawn position within the entity's hitbox.
    *   `1` (True)

### LifetimeComponent

This component determines how long the particle remains active.

*   **`lifetime`**: The duration of the particle in seconds.
    *   `20`