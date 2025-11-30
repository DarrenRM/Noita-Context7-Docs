---
title: Red Smoke Pillar Top-Left Particle
category: entities
---

---

# Red Smoke Pillar Top-Left Particle

This entity defines a particle effect that generates red smoke, typically used for top-left directional explosions.

## Key Components

### VelocityComponent
Controls the particle's movement and interaction with physics.

*   `gravity_y`: `0` - No vertical gravity applied.
*   `air_friction`: `7.0` - Significant air friction to slow the particle.

### SimplePhysicsComponent
Enables basic physics interactions for the particle.

### SetStartVelocityComponent
Determines the initial velocity of the particle.

*   `randomize_speed.min`: `120`
*   `randomize_speed.max`: `140`
*   `randomize_angle.min`: `3.14159` (approx. 180 degrees)
*   `randomize_angle.max`: `3.34159` (slightly more than 180 degrees, suggesting a slight upward and leftward initial push)

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   `min_speed`: `50` - The particle will disappear if its speed drops below this value.

### SpriteParticleEmitterComponent
The core component responsible for emitting and defining the visual properties of the smoke particles.

*   `sprite_file`: `data/particles/smoke_cloud_tiny_red_$[1-4].xml` - Specifies the sprite files to be used, with a random selection from `smoke_cloud_tiny_red_1` to `smoke_cloud_tiny_red_4`.
*   `emission_interval_min_frames`: `4`
*   `emission_interval_max_frames`: `4` - Particles are emitted at a consistent rate.
*   `additive`: `1` - Particles are rendered additively, meaning they contribute to the brightness of what's behind them.
*   `emissive`: `0` - Particles do not emit light themselves.
*   `scale.x`, `scale.y`: `1.0` - Base scale of the emitted sprites.
*   `sprite_random_rotation`: `1` - Emitted sprites will have random rotations.
*   `randomize_scale.min_x`, `randomize_scale.max_x`, `randomize_scale.min_y`, `randomize_scale.max_y`: Controls slight random variations in scale for each particle.
*   `randomize_velocity.min_y`, `randomize_velocity.max_y`: Controls random vertical velocity for emitted particles (slightly upwards).
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`: Controls random horizontal velocity for emitted particles (slightly leftwards).
*   `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`: Adds slight random offsets to the emission position of each particle.
*   `randomize_animation_speed_coeff.min`, `randomize_animation_speed_coeff.max`: Controls random variations in the animation speed of the emitted sprites.
*   `render_back`: `1` - Particles are rendered behind other elements.