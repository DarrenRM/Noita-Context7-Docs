---
title: Blue Fast Swirl Explosion Trail Particle
category: entities
---

---

# Blue Fast Swirl Explosion Trail Particle

This document describes the configuration for a particle entity in Noita, specifically designed to create a fast-moving, blue, swirling trail effect often associated with explosions.

## Key Components and Attributes

This particle utilizes several components to define its behavior, appearance, and emission.

### VelocityComponent

Controls the basic physics of the particle.

| Attribute      | Value | Description                                     |
|----------------|-------|-------------------------------------------------|
| `gravity_y`    | `0`   | No vertical gravity applied.                    |
| `air_friction` | `2`   | Moderate air friction, slowing the particle.    |
| `updates_velocity` | `1` | Enables velocity updates based on other components. |

### SimplePhysicsComponent

A foundational component for physics simulation. No specific attributes are set here, implying default behavior.

### SetStartVelocityComponent

Determines the initial speed and direction of the emitted particles.

| Attribute              | Value      | Description                                                              |
|------------------------|------------|--------------------------------------------------------------------------|
| `randomize_speed.min`  | `450`      | Minimum initial speed in pixels per second.                              |
| `randomize_speed.max`  | `600`      | Maximum initial speed in pixels per second.                              |
| `randomize_angle.min`  | `0`        | Minimum initial angle in radians (0 radians = right).                    |
| `randomize_angle.max`  | `6.283185` | Maximum initial angle in radians (approximately 2π, a full circle). |

### ParticleEmitterComponent

This is the core component responsible for generating and managing the particles.

| Attribute                 | Value      | Description