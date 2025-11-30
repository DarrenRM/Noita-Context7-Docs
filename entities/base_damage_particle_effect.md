---
title: Base Damage Particle Effect
category: entities
---

# Base Damage Particle Effect

This entity defines a particle effect that is applied when a "base damage" effect is active. It's primarily used for visual feedback.

## Key Components

### `InheritTransformComponent`

This component ensures the particle effect inherits the transform (position, rotation, scale) of its parent entity.

*   `_tags`: `enabled_in_world`, `enabled_in_hand` - The effect is active in both the game world and when held in hand.
*   `Transform`:
    *   `position.x`: `8` - Offset on the X-axis.
    *   `position.y`: `0` - Offset on the Y-axis.

### `SpriteParticleEmitterComponent`

This is the core component responsible for generating and managing the particles.

*   `_tags`: `enabled_in_hand`, `item_identified` - The effect is active when held and when the item is identified.
*   `sprite_file`: `data/particles/tinyspark_01.xml` - Specifies the sprite used for each particle.
*   `delay`: `0` - No initial delay before emission starts.
*   `lifetime`: `0` - Particles have no inherent lifetime and are managed by other properties.
*   `color.r`, `color.g`, `color.b`, `color.a`: `1` - Initial color is white (fully opaque).
*   `color_change`: `0` for all channels - Color does not change over the particle's life.
*   `velocity.x`, `velocity.y`: `0` - Initial velocity is zero.
*   `gravity.y`: `10` - Particles are affected by gravity pulling them downwards.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `25`, `35` - Particles are emitted every 25 to 35 frames.
*   `count_min`, `count_max`: `1`, `1` - Exactly one particle is emitted per emission interval.
*   `randomize_rotation`: `-0.3415` to `0.3415` - Particles have a slight random initial rotation.
*   `randomize_position`:
    *   `min_x`: `-5`, `max_x`: `5` - Particles spawn within a horizontal range of 5 units.
    *   `min_y`: `0`, `max_y`: `0` - No vertical randomization in spawn position.
*   `randomize_velocity`:
    *   `min_x`: `-10`, `max_x`: `10` - Particles have a random horizontal velocity.
    *   `min_y`: `-20`, `max_y`: `5` - Particles have a random upward/downward velocity, with a bias towards upward movement.