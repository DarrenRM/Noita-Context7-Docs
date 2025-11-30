---
title: Unstable Polymorph Effect
category: entities
---

# Unstable Polymorph Effect

This entity defines an unstable polymorph effect, which transforms the player into a sheep after a set duration. It also triggers an explosion and plays a sound effect.

## Key Components

### GameEffectComponent
This component governs the core behavior of the polymorph effect.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `effect`            | Specifies the type of game effect. Set to `POLYMORPH_UNSTABLE`.             |
| `frames`            | The duration of the effect in frames (1200 frames ≈ 20 seconds).            |
| `disable_movement`  | If set to `1`, movement is disabled during the effect. Here, it's `0`.      |
| `polymorph_target`  | The entity that the player will be polymorphed into. Here, it's `sheep.xml`. |

### Entity (Explosion)
This nested entity defines the visual and particle effects associated with the polymorph.

#### SpriteParticleEmitterComponent
Controls the sprite-based particles for the explosion.

| Attribute              | Description