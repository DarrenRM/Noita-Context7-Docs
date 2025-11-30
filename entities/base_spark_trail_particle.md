---
title: Base Spark Trail Particle
category: entities
---

# Base Spark Trail Particle

This entity defines the behavior and appearance of a basic spark trail particle effect in Noita. It's designed to be a foundational element for creating more complex particle effects.

## Key Components and Attributes

This entity utilizes several components to manage its physics, emission, and visual properties.

### VelocityComponent

Controls the basic physics of the particle.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `gravity_y`   | The downward force of gravity applied to the particle. |
| `air_friction`| The resistance the particle experiences from the air. |

### SimplePhysicsComponent

A placeholder component, likely for future physics interactions or simpler physics handling.

### SetStartVelocityComponent

Determines the initial speed and direction of the emitted particles.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `randomize_speed.min` | The minimum initial speed of the particle.                               |
| `randomize_speed.max` | The maximum initial speed of the particle.                               |
| `randomize_angle.min` | The minimum initial angle (in radians) for particle direction.           |
| `randomize_angle.max` | The maximum initial angle (in radians) for particle direction.           |

### DieIfSpeedBelowComponent

Causes the particle to be destroyed if its speed drops below a certain threshold.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `min_speed` | The minimum speed required for the particle to persist. |

### ParticleEmitterComponent (Multiple Instances)

These components are responsible for generating the actual particles that form the trail. The entity has three `ParticleEmitterComponent` instances, each with distinct configurations for different aspects of the effect.

#### Emitter 1: Primary Sparks

This emitter generates the main "spark" particles.

| Attribute                   | Description