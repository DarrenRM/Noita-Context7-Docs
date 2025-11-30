---
title: Gunpowder Smoke Particle
category: entities/particles
---

# Gunpowder Smoke Particle

This entity defines the visual and physical properties of gunpowder smoke particles used in explosions.

## Key Components

### VelocityComponent
Controls the particle's movement and interaction with physics.
- `gravity_y`: "500" - Applies a downward gravitational force.
- `air_friction`: "10.0" - Slows down the particle due to air resistance.

### SimplePhysicsComponent
Enables basic physics interactions for the particle.

### SetStartVelocityComponent
Determines the initial velocity of emitted particles.
- `randomize_speed.min`: "100" - Minimum initial speed.
- `randomize_speed.max`: "500" - Maximum initial speed.
- `randomize_angle.min`: "0" - Minimum initial direction angle (radians).
- `randomize_angle.max`: "6.283185" - Maximum initial direction angle (radians, full circle).

### SpriteParticleEmitterComponent
Manages the emission and appearance of smoke sprites.
- `sprite_file`: "data/particles/smoke_gunpowder_0$[1-4].xml" - Specifies the sprite textures to use, with a range for variation.
- `emission_interval_min_frames`: "1" - Minimum frames between emissions.
- `emission_interval_max_frames`: "2" - Maximum frames between emissions.
- `additive`: "0" - Disables additive blending for sprites.
- `emissive`: "0" - Disables emissive properties for sprites.
- `scale.x`, `scale.y`: "1.0" - Default scale of the sprites.
- `sprite_random_rotation`: "1" - Enables random rotation for each sprite.
- `randomize_scale.min_x`, `randomize_scale.max_x`: "-0.1" to "0.1" - Random variation in X-axis scale.
- `randomize_scale.min_y`, `randomize_scale.max_y`: "-0.1" to "0.1" - Random variation in Y-axis scale.
- `randomize_velocity.min_y`, `randomize_velocity.max_y`: "-10" to "0" - Random vertical velocity adjustment.
- `randomize_velocity.min_x`, `randomize_velocity.max_x`: "-10" to "10" - Random horizontal velocity adjustment.
- `lifetime`: "0.5" - Duration each emitted particle exists.
- `velocity_slowdown`: "5.8" - Rate at which particle velocity decreases over time.

### LifetimeComponent
Determines the total lifespan of the entity itself.
- `lifetime`: "4" - The entity (and its associated particles) will exist for 4 seconds.