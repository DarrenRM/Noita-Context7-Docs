---
title: Heal/Hurt Effect Entity
category: entities
---

# Heal/Hurt Effect Entity

This entity defines a basic healing or hurting effect, primarily used for particles.

## Key Components

### Base Entity (`<Base>`)
This component inherits from a base particle entity, likely `data/entities/particles/heal.xml`.

### Sprite Particle Emitter (`<SpriteParticleEmitterComponent>`)
Configures the emission of particles for the effect.

*   **`emission_interval_min_frames`**: Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: Maximum frames between particle emissions.
*   **`randomize_position_inside_hitbox`**: Whether particle positions are randomized within the hitbox.

### Game Effect (`<GameEffectComponent>`)
Applies a specific game effect.

*   **`effect`**: The type of effect to apply. Common values include `REGENERATION` (for healing) or `DAMAGE` (for hurting).
*   **`frames`**: The duration of the effect in frames.

### Inherit Transform (`<InheritTransformComponent>`)
This component, when enabled, allows the entity to inherit transformations from its parent.