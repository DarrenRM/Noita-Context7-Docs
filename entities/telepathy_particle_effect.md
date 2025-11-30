---
title: Telepathy Particle Effect
category: entities
---

# Telepathy Particle Effect

This document describes the configuration for the "Telepathy" particle effect in Noita, primarily focusing on its visual and emission properties.

## SpriteParticleEmitterComponent

This component defines the behavior and appearance of the particles emitted.

### Key Attributes:

*   **`sprite_file`**: Specifies the sprite used for the particles.
    *   `data/particles/ray.xml`: Indicates the particles are based on a "ray" sprite.
*   **`lifetime`**: The duration each particle exists.
    *   `0.8`: Particles last for 0.8 seconds.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: The initial color of the particles.
    *   `1, 1, 1, 0.5`: Starts as white with 50% opacity.
*   **`color_change.a`**: How the alpha (opacity) of the particle changes over its lifetime.
    *   `-3`: The opacity decreases significantly over time.
*   **`gravity.y`**: The gravitational pull affecting the particles.
    *   `10`: A moderate downward pull.
*   **`use_velocity_as_rotation`**: Whether particle rotation follows its velocity.
    *   `1`: Rotation is driven by the particle's movement.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y`**: Defines the range of random initial velocities.
    *   `min_x="-40"`, `max_x="40"`, `min_y="-40"`, `max_y="40"`: Particles are emitted with a random velocity within a square area.
*   **`randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`**: Defines the range of random initial positions relative to the emitter.
    *   `min_x="-5"`, `max_x="5"`, `min_y="-5"`, `max_y="5"`: Particles spawn within a small area around the emitter.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The frame range for emitting new particles.
    *   `6` to `12`: New particles are emitted every 6 to 12 frames.
*   **`count_min`, `count_max`**: The number of particles emitted per interval.
    *   `1` to `1`: Exactly one particle is emitted at a time.
*   **`velocity_always_away_from_center`**: Whether particles are always pushed away from the emitter's center.
    *   `1`: Particles will move outwards.

## LightComponent

This component adds a light source to the entity.

### Key Attributes:

*   **`radius`**: The radius of the light's influence.
    *   `60`: The light extends 60 units.
*   **`r`, `g`, `b`**: The RGB color values of the light.
    *   `80, 60, 10`: A yellowish-orange light.