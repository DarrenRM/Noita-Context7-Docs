---
title: Charm One-Off Particle
category: entities/particles
---

---

# Charm One-Off Particle

This entity defines a single-use particle effect, likely used for visual feedback or temporary effects in Noita. It inherits its base properties from `charm.xml` and adds specific lifetime and emission behaviors.

## Key Components

### Base Entity (`<Base file="data/entities/particles/charm.xml">`)

This indicates that `charm_oneoff.xml` extends the functionality of the base `charm.xml` particle entity. Specific overrides or additions are defined within this entity.

### Sprite Particle Emitter Component (`<SpriteParticleEmitterComponent>`)

This component controls the emission of sprite-based particles.

*   **`emission_interval_min_frames`**: The minimum number of frames between particle emissions.
    *   Value: `5`
*   **`emission_interval_max_frames`**: The maximum number of frames between particle emissions.
    *   Value: `15`
*   **`randomize_position_inside_hitbox`**: Determines if particles are emitted randomly within the entity's hitbox.
    *   Value: `1` (True)

### Lifetime Component (`<LifetimeComponent>`)

This component defines how long the particle entity exists.

*   **`lifetime`**: The duration in frames for which the particle entity will persist.
    *   Value: `20`