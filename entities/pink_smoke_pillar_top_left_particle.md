---
title: Pink Smoke Pillar Top Left Particle
category: entities
---

# Pink Smoke Pillar Top Left Particle

This entity defines a particle effect that generates pink smoke, typically used as a visual element in explosions. It's designed to emit small, randomized smoke sprites with specific velocity and positional adjustments.

## Key Components

### VelocityComponent
Controls the particle's movement and interaction with air.

| Attribute      | Value | Description                                     |
|----------------|-------|-------------------------------------------------|
| `gravity_y`    | `0`   | No vertical gravity applied to the particle.    |
| `air_friction` | `7.0` | High air friction, causing particles to slow down. |

### SimplePhysicsComponent
Indicates that the entity has basic physics properties.

### SetStartVelocityComponent
Determines the initial speed and direction of the emitted particles.

| Attribute                 | Value   | Description                                                              |
|---------------------------|---------|--------------------------------------------------------------------------|
| `randomize_speed.min`     | `120`   | Minimum initial speed.                                                   |
| `randomize_speed.max`     | `140`   | Maximum initial speed.                                                   |
| `randomize_angle.min`     | `3.14159` | Minimum emission angle (approximately 180 degrees).                      |
| `randomize_angle.max`     | `3.34159` | Maximum emission angle (slightly more than 180 degrees). This suggests an upward-left direction. |

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

| Attribute   | Value | Description                                     |
|-------------|-------|-------------------------------------------------|
| `min_speed` | `50`  | Particle is destroyed if its speed drops below 50. |

### SpriteParticleEmitterComponent
The core component responsible for emitting and managing the smoke sprites.

| Attribute                         | Value   | Description