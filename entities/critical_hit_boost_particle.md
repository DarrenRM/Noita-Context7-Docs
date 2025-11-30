---
title: Critical Hit Boost Particle
category: entities
---

---

# Critical Hit Boost Particle

This entity defines a particle effect associated with the "Critical Hit Boost" perk in Noita. It inherits its base behavior from `berserk.xml` and customizes its particle emission.

## Key Components

### Base Entity

*   **`file="data/entities/particles/berserk.xml"`**: Inherits core particle properties and behaviors from the `berserk` particle entity.

### SpriteParticleEmitterComponent

This component controls the emission of sprite-based particles.

*   **`emission_interval_min_frames="30"`**: The minimum number of frames between particle emissions.
*   **`emission_interval_max_frames="60"`**: The maximum number of frames between particle emissions.
*   **`randomize_position_inside_hitbox="1"`**: Particles will be emitted at a random position within the entity's hitbox.

### InheritTransformComponent

*   This component ensures that the particle inherits the transform (position, rotation, scale) of its parent entity.