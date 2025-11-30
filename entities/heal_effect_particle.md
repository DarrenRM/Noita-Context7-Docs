---
title: Heal Effect Particle
category: entities
---

# Heal Effect Particle

This document describes the `particle_heal_effect` entity, which is used to generate visual and auditory feedback for healing effects in Noita. It primarily utilizes `SpriteParticleEmitterComponent` to create visual particles and `AudioComponent` for sound.

## Key Components

### SpriteParticleEmitterComponent (Small Sparkles)

This component defines the behavior of the smaller, "sparkly" particles associated with healing.

*   **`sprite_file`**: `data/particles/heal_small.xml` - Specifies the sprite sheet or animation to use for these particles.
*   **`lifetime`**: `0.75` - The base duration each particle exists.
*   **`randomize_lifetime`**:
    *   `min`: `0.5`
    *   `max`: `1.0` - Introduces variation in particle lifespan.
*   **`emission_interval_min_frames`**: `2`
*   **`emission_interval_max_frames`**: `15` - Controls the timing between particle emissions.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Each emission spawns a single particle.
*   **`additive`**: `1` - Particles are rendered additively, making them appear brighter when overlapping.
*   **`emissive`**: `0` - Particles do not emit light themselves.
*   **`sprite_random_rotation`**: `1` - Particles will have random initial rotations.
*   **`gravity.y`**: `-5` - Particles are affected by upward gravity.
*   **`randomize_velocity`**:
    *   `min_y`: `-10`
    *   `max_y`: `10`
    *   `min_x`: `-10`
    *   `max_x`: `10` - Particles are emitted with randomized velocity in both X and Y directions.
*   **`randomize_position`**:
    *   `min_x`: `-7`
    *   `max_x`: `7`
    *   `min_y`: `-10`
    *   `max_y`: `10` - Particles are spawned with slight positional offsets.
*   **`velocity_slowdown`**: `0.5` - Particles lose velocity over time.
*   **`randomize_animation_speed_coeff`**:
    *   `min`: `0.667`
    *   `max`: `1.0` - Randomizes the animation speed of the particle sprites.

### LifetimeComponent

*   **`lifetime`**: `180` - The total duration this entity (and its associated particles) will exist. This is a relatively long duration, suggesting it's tied to a sustained healing effect.

### AudioComponent

*   **`file`**: `data/audio/Desktop/misc.bank` - Specifies the audio bank containing the sound event.
*   **`event_root`**: `game_effect/regeneration` - The specific sound event triggered for regeneration or healing.

### SpriteParticleEmitterComponent (Bigger Blinkys - Commented Out)

The commented-out section shows an example of another `SpriteParticleEmitterComponent` that could be used for larger, "blinky" particles. This demonstrates a pattern for adding more visual elements to effects. Key differences in this commented section include:

*   **`sprite_file`**: `data/particles/shine_07.xml` - Uses a different sprite.
*   **`lifetime`**: `1.5` - Longer individual particle lifetime.
*   **`emission_interval_max_frames`**: `120` - Less frequent emissions.
*   **`gravity.y`**: `5` - Particles are affected by downward gravity.
*   **`randomize_position`**: Larger positional randomization ranges (`-100` to `100` for X, `-150` to `50` for Y), suggesting a wider spread.