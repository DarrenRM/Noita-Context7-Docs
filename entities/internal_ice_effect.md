---
title: Internal Ice Effect
category: entities
---

# Internal Ice Effect

This entity defines the internal ice effect in Noita. It's a simple entity primarily used to apply a status effect to entities.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `effect`       | The type of effect to apply. Set to `INTERNAL_ICE`. |
| `frames`       | The duration of the effect in frames (10 frames). |
| `disable_movement` | Whether movement is disabled by this effect (0 means not disabled). |