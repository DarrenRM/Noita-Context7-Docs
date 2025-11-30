---
title: Teleportation Source Particle Emitter
category: entities
---

---

# Teleportation Source Particle Emitter

This document describes the XML configuration for a particle emitter used to create a visual effect for teleportation sources in Noita.

## Entity: `explosion`

This entity defines the particle emitter itself.

### Key Components:

*   **`SpriteParticleEmitterComponent`**: This is the core component responsible for generating and managing the particles.

    *   **`sprite_file`**: `data/particles/teleparticle.xml` - Specifies the sprite definition for each individual particle.
    *   **`lifetime`**: `0.4` - The duration each particle exists in seconds.
    *   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 1` - The initial color of the particles (white).
    *   **`color_change.a`**: `-0.2` - The rate at which the alpha (transparency) of the particles decreases over their lifetime, causing them to fade out.
    *   **`velocity.x`, `velocity.y`**: `0, 0` - The base velocity applied to particles.
    *   **`scale.x`, `scale.y`**: `1, 0.2` - The initial scale of the particles.
    *   **`scale_velocity.x`, `scale_velocity.y`**: `-0.2, 1` - The rate at which the scale of the particles changes over their lifetime. This creates a stretching effect.
    *   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1, 1` - Particles are emitted every frame.
    *   **`count_min`, `count_max`**: `4, 5` - The number of particles emitted per emission event.
    *   **`randomize_position.min_x`, `randomize_position.max_x`**: `-5, 5` - Random horizontal offset for particle emission.
    *   **`randomize_velocity.min_y`, `randomize_velocity.max_y`**: `-40, 40` - Random vertical velocity applied to particles, creating a spread.
    *   **`randomize_lifetime.min`, `randomize_lifetime.max`**: `-0.45, 0.2` - Random variation in particle lifetime.

*   **`LifetimeComponent`**: Manages the lifetime of the entity itself.

    *   **`lifetime`**: `5` - The total duration this particle emitter entity will exist in seconds.
    *   **`kill_parent`**: `1` - Indicates that when this entity dies, it should also kill its parent entity (if any).