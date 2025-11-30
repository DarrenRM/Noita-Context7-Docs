---
title: Berserk Effect Entity
category: entities
---

# Berserk Effect Entity

This entity defines the visual and functional components of the Berserk effect in Noita. It primarily utilizes a particle emitter for visual representation and a `GameEffectComponent` to apply the actual Berserk status to entities.

## Key Components

### Base Entity (`<Base file="data/entities/particles/berserk.xml">`)

This tag indicates that the entity inherits properties from a base particle entity.

### Sprite Particle Emitter Component (`<SpriteParticleEmitterComponent>`)

This component controls the emission of particles that visually represent the Berserk effect.

*   **`emission_interval_min_frames`**: The minimum number of frames between particle emissions.
    *   Value: `10`
*   **`emission_interval_max_frames`**: The maximum number of frames between particle emissions.
    *   Value: `20`
*   **`randomize_position_inside_hitbox`**: Whether to randomize particle emission positions within the entity's hitbox.
    *   Value: `1` (Enabled)

### Inherit Transform Component (`<InheritTransformComponent>`)

This component allows the entity to inherit transformations (position, rotation, scale) from its parent.

*   **`_enabled`**: Controls whether the component is active.
    *   Value: `1` (Enabled)

### Game Effect Component (`<GameEffectComponent>`)

This component applies a specific game effect to entities.

*   **`effect`**: The type of game effect to apply.
    *   Value: `BERSERK`
*   **`frames`**: The duration of the effect in frames.
    *   Value: `3600` (Equivalent to 1 minute at 60 FPS)