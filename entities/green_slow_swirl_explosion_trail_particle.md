---
title: Green Slow Swirl Explosion Trail Particle
category: entities
---

# Green Slow Swirl Explosion Trail Particle

This entity defines a particle effect that creates a green, slow-swirling trail, often used in explosions. It utilizes a combination of physics, particle emission, and a custom Lua script for its movement behavior.

## Key Components

### VelocityComponent
This component controls the basic velocity and movement of the particle.

| Attribute      | Value | Description                                     |
| -------------- | ----- | ----------------------------------------------- |
| `gravity_y`    | `0`   | Disables vertical gravity for this particle.    |
| `air_friction` | `2`   | Applies a moderate amount of air friction.      |
| `updates_velocity` | `1` | Enables velocity updates based on other components. |

### SimplePhysicsComponent
A basic physics component, likely used in conjunction with other physics-related components.

### SetStartVelocityComponent
This component defines the initial velocity of the particles when they are emitted.

| Attribute             | Value     | Description                                                                 |
| --------------------- | --------- | --------------------------------------------------------------------------- |
| `randomize_speed.min` | `50`      | Minimum initial speed of the emitted particle.                              |
| `randomize_speed.max` | `200`     | Maximum initial speed of the emitted particle.                              |
| `randomize_angle.min` | `0`       | Minimum initial angle (in radians) for the particle's velocity.             |
| `randomize_angle.max` | `6.283185`| Maximum initial angle (in radians) for the particle's velocity (full circle). |

### ParticleEmitterComponent
This is the core component responsible for emitting the particles that form the trail.

| Attribute                 | Value   | Description