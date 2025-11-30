---
title: Gold Dust Particles
category: entities
---

# Gold Dust Particles

This document describes the `gold_dust.xml` entity, which defines the visual particles associated with gold dust in Noita. It utilizes two `SpriteParticleEmitterComponent` instances to create distinct visual effects.

## Key Components

### SpriteParticleEmitterComponent (Small Sparkys)

This component defines the emission of smaller, spark-like particles.

*   **`sprite_file`**: `data/particles/shine_08.xml` - Specifies the sprite texture to be used for these particles.
*   **`lifetime`**: `1.5` - The base duration each particle exists.
*   **`randomize_lifetime`**:
    *   `min`: `1.0`
    *   `max`: `2.0` - Introduces variation to the particle lifetime.
*   **`emission_interval_min_frames`**: `2`
*   **`emission_interval_max_frames`**: `40` - Controls the timing between particle emissions.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Each emission spawns a single particle.
*   **`additive`**: `1` - Particles are rendered additively, contributing to brightness.
*   **`emissive`**: `0` - Particles do not emit light themselves.
*   **`sprite_random_rotation`**: `1` - Particles will have random initial rotations.
*   **`gravity.y`**: `5` - Particles are affected by gravity pulling them downwards.
*   **`randomize_velocity`**:
    *   `min_y`: `-10`
    *   `max_y`: `10`
    *   `min_x`: `-10`
    *   `max_x`: `10` - Particles are emitted with randomized velocities in both X and Y directions.
*   **`randomize_position`**:
    *   `min_x`: `-150`
    *   `max_x`: `150`
    *   `min_y`: `-200`
    *   `max_y`: `50` - Particles are emitted within a randomized area relative to the emitter's position.
*   **`velocity_slowdown`**: `0.5` - Particles gradually lose velocity over time.
*   **`randomize_animation_speed_coeff`**:
    *   `min`: `0.667`
    *   `max`: `1.0` - The animation speed of the particle sprite is randomized.

### SpriteParticleEmitterComponent (Bigger Blinkys)

This component defines the emission of larger, more prominent particles.

*   **`sprite_file`**: `data/particles/shine_07.xml` - Specifies the sprite texture for these larger particles.
*   **`lifetime`**: `1.5` - The base duration each particle exists.
*   **`randomize_lifetime`**:
    *   `min`: `0.5`
    *   `max`: `2.0` - Introduces variation to the particle lifetime.
*   **`emission_interval_min_frames`**: `2`
*   **`emission_interval_max_frames`**: `120` - Controls the timing between particle emissions.
*   **`additive`**: `1` - Particles are rendered additively.
*   **`emissive`**: `0` - Particles do not emit light.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Each emission spawns a single particle.
*   **`sprite_random_rotation`**: `1` - Particles will have random initial rotations.
*   **`gravity.y`**: `5` - Particles are affected by gravity.
*   **`randomize_velocity`**:
    *   `min_y`: `-10`
    *   `max_y`: `10`
    *   `min_x`: `-10`
    *   `max_x`: `10` - Particles are emitted with randomized velocities.
*   **`randomize_position`**:
    *   `min_x`: `-100`
    *   `max_x`: `100`
    *   `min_y`: `-150`
    *   `max_y`: `50` - Particles are emitted within a randomized area.
*   **`velocity_slowdown`**: `0.5` - Particles gradually lose velocity.
*   **`randomize_animation_speed_coeff`**:
    *   `min`: `0.667`
    *   `max`: `1.0` - The animation speed of the particle sprite is randomized.