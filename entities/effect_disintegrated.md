---
title: Effect Disintegrated
category: entities
---

# Effect Disintegrated

This entity defines a visual and physical effect for when an entity is "disintegrated". It's primarily used for ragdoll effects.

## Key Components

### GameEffectComponent

This component dictates the behavior and appearance of the disintegration effect.

| Attribute        | Description                                                                                                |
| :--------------- | :--------------------------------------------------------------------------------------------------------- |
| `effect`         | The type of game effect. `NONE` indicates this component doesn't apply a standard game effect itself.      |
| `frames`         | The number of frames the disintegration animation or effect will last. Set to `5` here.                     |
| `disable_movement` | Whether movement is disabled during the effect. `0` means movement is *not* disabled.                    |
| `ragdoll_effect` | Specifies the type of ragdoll effect to apply. `DISINTEGRATED` is the key value here.                      |
| `ragdoll_material` | The material that the ragdoll will be treated as during the disintegration. `soil` is used in this case. |