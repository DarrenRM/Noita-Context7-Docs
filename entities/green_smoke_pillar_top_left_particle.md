---
title: Green Smoke Pillar Top Left Particle
category: entities
---

# Green Smoke Pillar Top Left Particle

This entity defines a particle effect that generates green smoke, typically used as part of an explosion. It focuses on controlling the movement and visual appearance of the emitted smoke particles.

## Key Components

### VelocityComponent
Controls the basic physics of the particle.

*   `gravity_y`: Set to `0`, meaning no gravity affects the particle.
*   `air_friction`: Set to `7.0`, indicating significant air resistance.

### SimplePhysicsComponent
A basic physics component, likely for simpler interactions.

### SetStartVelocityComponent
Determines the initial velocity of the particle.

*   `randomize_speed.min`: Minimum initial speed of `120`.
*   `randomize_speed.max`: Maximum initial speed of `140`.
*   `randomize_angle.min`: Minimum initial angle in radians (`3.14159` or 180 degrees).
*   `randomize_angle.max`: Maximum initial angle in radians (`3.34159`).

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   `min_speed`: The particle will be destroyed if its speed drops below `50`.

### SpriteParticleEmitterComponent
This is the core component responsible for emitting the smoke particles.

*   `sprite_file`: Specifies the sprite to be used for the emitted particles. It uses a pattern `data/particles/smoke_cloud_tiny_green_$[1-4].xml`, suggesting multiple variations of a tiny green smoke cloud sprite.
*   `emission_interval_min_frames`: Particles are emitted every `4` frames (minimum).
*   `emission_interval_max_frames`: Particles are emitted every `4` frames (maximum), meaning a consistent emission rate.
*   `additive`: Set to `1`, indicating additive blending for the sprites, making them appear brighter when overlapping.
*   `emissive`: Set to `0`, meaning the particles do not emit light themselves.
*   `scale.x`, `scale.y`: Base scale of the emitted particles is `1.0`.
*   `sprite_random_rotation`: Set to `1`, meaning the emitted sprites will have random rotations.
*   `randomize_scale.min_x`, `randomize_scale.max_x`: Randomizes the X-scale of particles between `-0.1` and `0.1` relative to the base scale.
*   `randomize_scale.min_y`, `randomize_scale.max_y`: Randomizes the Y-scale of particles between `-0.1` and `0.1` relative to the base scale.
*   `randomize_velocity.min_y`, `randomize_velocity.max_y`: Randomizes the Y-velocity of emitted particles between `-10` and `0`.
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`: Randomizes the X-velocity of emitted particles between `-10` and `-5`.
*   `randomize_position.min_y`, `randomize_position.max_y`: Randomizes the emission position on the Y-axis between `-5` and `5`.
*   `randomize_position.min_x`, `randomize_position.max_x`: Randomizes the emission position on the X-axis between `-5` and `5`.
*   `randomize_animation_speed_coeff.min`, `randomize_animation_speed_coeff.max`: Randomizes the animation speed multiplier for the sprites between `0.667` and `1.5`.
*   `render_back`: Set to `1`, indicating that these particles should be rendered behind other elements.