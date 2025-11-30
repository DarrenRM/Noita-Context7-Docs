---
title: Grey Smoke Pillar Top Right Particle
category: entities
---

# Grey Smoke Pillar Top Right Particle

This entity defines a particle effect that generates grey smoke, intended to appear as a pillar rising from the top right. It utilizes a `SpriteParticleEmitterComponent` to spawn multiple smaller smoke particles with randomized properties.

## Key Components

### VelocityComponent
Controls the movement and air resistance of the main particle entity.

*   `gravity_y`: `0` - No vertical gravity applied to the main entity.
*   `air_friction`: `7.0` - Significant air friction, slowing down the entity.

### SimplePhysicsComponent
Indicates that the entity has basic physics properties.

### SetStartVelocityComponent
Defines the initial velocity applied to the particle when it spawns.

*   `randomize_speed.min`: `120` - Minimum initial speed.
*   `randomize_speed.max`: `140` - Maximum initial speed.
*   `randomize_angle.min`: `-0.2` - Minimum initial angle (slight downward bias).
*   `randomize_angle.max`: `0.0` - Maximum initial angle (horizontal).

### DieIfSpeedBelowComponent
Causes the particle entity to despawn if its speed drops below a certain threshold.

*   `min_speed`: `50` - The speed threshold for despawning.

### SpriteParticleEmitterComponent
The core component responsible for emitting the actual smoke particles.

*   `sprite_file`: `data/particles/smoke_cloud_tiny_grey_$[1-4].xml` - Specifies the sprite files for the emitted particles, using a wildcard for variations.
*   `emission_interval_min_frames`: `4` - Minimum frames between emissions.
*   `emission_interval_max_frames`: `4` - Maximum frames between emissions.
*   `additive`: `1` - Particles are rendered additively, making them brighter.
*   `emissive`: `0` - Particles are not emissive (don't emit light themselves).
*   `scale.x`, `scale.y`: `1.0` - Base scale of the emitted particles.
*   `sprite_random_rotation`: `1` - Emitted particles will have random rotation.
*   `randomize_scale.min_x`, `randomize_scale.max_x`: `-0.1` to `0.1` - Small random variation in X scale.
*   `randomize_scale.min_y`, `randomize_scale.max_y`: `-0.1` to `0.1` - Small random variation in Y scale.
*   `randomize_velocity.min_y`, `randomize_velocity.max_y`: `-10` to `0` - Emitted particles have a slight downward velocity bias.
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`: `5` to `10` - Emitted particles have a positive X velocity bias (moving right).
*   `randomize_position.min_y`, `randomize_position.max_y`: `-5` to `5` - Small random offset in Y position for emitted particles.
*   `randomize_position.min_x`, `randomize_position.max_x`: `-5` to `5` - Small random offset in X position for emitted particles.
*   `randomize_animation_speed_coeff.min`: `0.667` - Minimum multiplier for the animation speed of emitted particles.
*   `randomize_animation_speed_coeff.max`: `1.5` - Maximum multiplier for the animation speed of emitted particles.
*   `render_back`: `1` - Renders these particles behind other elements.