---
title: Internal Fire Effect Entity
category: entities
---

# Internal Fire Effect Entity

This entity defines the visual and auditory effects associated with the "INTERNAL_FIRE" game effect in Noita. It's primarily used to create a burning visual and sound when an entity is set on fire internally.

## Key Components

### GameEffectComponent

This component signifies that the entity is a game effect.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `effect`         | The type of game effect. Set to `INTERNAL_FIRE`.                         |
| `frames`         | The duration of the effect in frames (100 frames = ~1.67 seconds).       |
| `disable_movement` | If set to `1`, this effect would disable movement. Here it's `0`.       |

### ParticleEmitterComponent (Fire)

This component is responsible for emitting fire particles.

| Attribute                 | Description