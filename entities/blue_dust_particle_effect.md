---
title: Blue Dust Particle Effect
category: entities
---

# Blue Dust Particle Effect

This entity defines a particle effect that generates blue dust-like particles, often used for visual flair in Noita. It utilizes two `SpriteParticleEmitterComponent` instances to create variations in particle appearance and behavior, along with a `LightComponent` to add a subtle glow.

## Key Components

### SpriteParticleEmitterComponent (Primary)

This component is responsible for emitting the main batch of blue dust particles.

*   **`sprite_file`**: `data/particles/shine_blue.xml` - Specifies the sprite used for these particles.
*   **`lifetime`**: `1.5` - The base duration each particle exists.
*   **`randomize_lifetime`**:
    *   `min`: `1.0`
    *   `max`: `2.0` - Adds variation to the particle's lifespan.
*   **`emission_interval_min_frames`**: `2`
*   **`emission_interval_max_frames`**: `30` - Controls how frequently new particles are emitted.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Each emission spawns a single particle.
*   **`additive`**: `1` - Particles are rendered additively, blending with the background.
*   **`emissive`**: `0` - Particles do not emit light themselves.
*   **`sprite_random_rotation`**: `1` - Particles will have a random initial rotation.
*   **`gravity.y`**: `5` - Particles are affected by gravity pulling them downwards.
*   **`randomize_velocity`**:
    *   `min_y`: `-10`
    *   `max_y`: `10`
    *   `min_x`: `-10`
    *   `max_x`: `10` - Provides random initial velocity to particles.
*   **`randomize_position`**:
    *   `min_x`: `-150`
    *   `max_x`: `150`
    *   `min_y`: `-200`
    *   `max_y`: `50` - Defines the area where particles are spawned relative to the entity's origin.
*   **`velocity_slowdown`**: `0.5` - Particles gradually lose velocity over time.
*   **`randomize_animation_speed_coeff`**:
    *   `min`: `0.667`
    *   `max`: `1.0` - Varies the animation speed of the particle sprites.

### SpriteParticleEmitterComponent (Secondary)

This component emits a different type of particle, likely for a more subtle or varied effect.

*   **`sprite_file`**: `data/particles/tinyspark_03.xml` - Uses a different sprite for these particles.
*   **`lifetime`**: `1.5` - Base lifespan.
*   **`randomize_lifetime`**:
    *   `min`: `0.5`
    *   `max`: `2.0` - Variation in lifespan.
*   **`emission_interval_min_frames`**: `2`
*   **`emission_interval_max_frames`**: `80` - Slower emission rate compared to the primary emitter.
*   **`additive`**: `1` - Additive blending.
*   **`emissive`**: `0` - Not emissive.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Single particle per emission.
*   **`sprite_random_rotation`**: `1` - Random initial rotation.
*   **`gravity.y`**: `5` - Affected by gravity.
*   **`randomize_velocity`**:
    *   `min_y`: `-10`
    *   `max_y`: `10`
    *   `min_x`: `-10`
    *   `max_x`: `10` - Random initial velocity.
*   **`randomize_position`**:
    *   `min_x`: `-100`
    *   `max_x`: `100`
    *   `min_y`: `-150`
    *   `max_y`: `50` - Spawn area.
*   **`velocity_slowdown`**: `0.5` - Gradual velocity reduction.
*   **`randomize_animation_speed_coeff`**:
    *   `min`: `0.667`
    *   `max`: `1.0` - Animation speed variation.

### LightComponent

This component adds a blue light source to the entity.

*   **`radius`**: `300` - The area of influence for the light.
*   **`r`**: `00`
*   **`g`**: `20`
*   **`b`**: `255` - Defines the blue color of the light.