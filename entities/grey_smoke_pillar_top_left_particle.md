---
title: Grey Smoke Pillar Top Left Particle
category: entities
---

# Grey Smoke Pillar Top Left Particle

This entity defines a particle effect that generates grey smoke, typically used for the top-left portion of an explosion. It utilizes a `SpriteParticleEmitterComponent` to spawn smaller smoke particles with randomized properties.

## Key Components

### VelocityComponent
Controls the movement and air resistance of the particle.

*   `gravity_y`: Set to `0`, meaning no gravity affects this particle.
*   `air_friction`: Set to `7.0`, indicating significant air resistance.

### SimplePhysicsComponent
A basic physics component, likely for simple collision or interaction handling.

### SetStartVelocityComponent
Determines the initial velocity of the particle.

*   `randomize_speed.min`: Minimum initial speed of `120`.
*   `randomize_speed.max`: Maximum initial speed of `140`.
*   `randomize_angle.min`: Minimum initial angle in radians (`3.14159` or 180 degrees).
*   `randomize_angle.max`: Maximum initial angle in radians (`3.34159` or approximately 191.5 degrees).

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   `min_speed`: The particle will be destroyed if its speed drops below `50`.

### SpriteParticleEmitterComponent
The core component responsible for emitting other particles (the smoke).

*   `sprite_file`: Specifies the sprite to be used for the emitted particles. It uses a pattern `data/particles/smoke_cloud_tiny_grey_$[1-4].xml`, indicating it will randomly pick one of four grey smoke cloud sprites.
*   `emission_interval_min_frames`: Minimum frames between emissions (`4`).
*   `emission_interval_max_frames`: Maximum frames between emissions (`4`). This means particles are emitted at a constant rate.
*   `additive`: Set to `1`, meaning the emitted particles use additive blending (they get brighter when overlapping).
*   `emissive`: Set to `0`, meaning the particles do not emit light themselves.
*   `scale.x`, `scale.y`: Base scale of the emitted particles (`1.0`).
*   `sprite_random_rotation`: Set to `1`, allowing emitted sprites to have random rotations.
*   `randomize_scale.min_x`, `randomize_scale.max_x`: Randomizes the X-scale of emitted particles between `-0.1` and `0.1` relative to the base scale.
*   `randomize_scale.min_y`, `randomize_scale.max_y`: Randomizes the Y-scale of emitted particles between `-0.1` and `0.1` relative to the base scale.
*   `randomize_velocity.min_y`, `randomize_velocity.max_y`: Randomizes the Y-velocity of emitted particles between `-10` and `0`.
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`: Randomizes the X-velocity of emitted particles between `-10` and `-5`.
*   `randomize_position.min_y`, `randomize_position.max_y`: Randomizes the Y-position of emitted particles within a range of `-5` to `5` relative to the emitter's position.
*   `randomize_position.min_x`, `randomize_position.max_x`: Randomizes the X-position of emitted particles within a range of `-5` to `5` relative to the emitter's position.
*   `randomize_animation_speed_coeff.min`, `randomize_animation_speed_coeff.max`: Randomizes the animation speed multiplier for emitted particles between `0.667` and `1.5`.
*   `render_back`: Set to `1`, meaning these particles will be rendered behind other elements.