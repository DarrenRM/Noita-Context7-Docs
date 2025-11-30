---
title: Explosion Trail Smoke Short Particle
category: entities
---

# Explosion Trail Smoke Short Particle

This entity defines a short-lived smoke trail particle used in explosions. It inherits its base behavior from `base_smoke_trail.xml` and modifies its initial velocity.

## Key Attributes

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml"`**: Inherits core properties and behaviors from a generic smoke trail particle.

### Velocity Component

*   **`SetStartVelocityComponent`**: This component controls the initial speed of the particle.
    *   **`randomize_speed.min="300"`**: The minimum initial speed for the particle.
    *   **`randomize_speed.max="400"`**: The maximum initial speed for the particle.

This particle is designed to be a quick, dissipating smoke effect, contributing to the visual impact of explosions.