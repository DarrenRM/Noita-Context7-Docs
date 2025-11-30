---
title: Polymorph Effect Entity
category: entities
---

# Polymorph Effect Entity

This entity defines the behavior and visual effects associated with the "Polymorph" game effect in Noita. When applied, it transforms the target into a different entity and triggers visual and auditory feedback.

## Key Components

### `GameEffectComponent`

This component is central to the polymorph effect.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `effect`            | Set to `"POLYMORPH"` to indicate the type of game effect.                   |
| `frames`            | Duration of the polymorph effect in frames (e.g., `600` frames = 10 seconds). |
| `disable_movement`  | If `1`, movement is disabled during the effect. `0` means movement is allowed. |
| `polymorph_target`  | Path to the XML file of the entity the target will be transformed into.     |

### `SpriteParticleEmitterComponent`

Responsible for generating puff-like particles during the polymorph transformation.

| Attribute                 | Description