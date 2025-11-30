---
title: Bouncy Orb Particle Effect
category: entities/particles
---

# Bouncy Orb Particle Effect

This entity defines a particle effect that creates a "bouncy orb" visual. It's primarily used for visual feedback when certain actions occur, likely related to bouncing or impact.

## Key Components

### LifetimeComponent

Controls how long the particle effect itself persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The duration in seconds the effect lasts. |

### ParticleEmitterComponent

Manages the emission of individual particles that make up the effect.

| Attribute                 | Description