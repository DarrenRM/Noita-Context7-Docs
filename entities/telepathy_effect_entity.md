---
title: Telepathy Effect Entity
category: entities
---

---

# Telepathy Effect Entity

This entity defines the visual and functional components of the Telepathy effect in Noita.

## Base Entity

The entity inherits its base properties from `data/entities/particles/telepathy.xml`.

## SpriteParticleEmitterComponent

This component controls the particle effects associated with the Telepathy.

### Key Attributes:

*   `randomize_position_inside_hitbox`: When set to `1`, particles will spawn randomly within the entity's hitbox, contributing to a more dynamic visual.

## InheritTransformComponent

This component is enabled (`_enabled="1"`) and likely ensures the effect's transform (position, rotation, scale) is inherited from its parent or the environment it's applied to.

## GameEffectComponent

This component applies the actual game effect.

### Key Attributes:

*   `effect`: Specifies the type of game effect to apply, which is `TELEPATHY` in this case.
*   `frames`: Defines the duration of the effect in frames. `1800` frames equates to 30 seconds (1800 frames / 60 frames per second).