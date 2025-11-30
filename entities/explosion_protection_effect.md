---
title: Explosion Protection Effect
category: entities
---

# Explosion Protection Effect

This entity defines a game effect that grants the player protection against explosions.

## Key Components

### GameEffectComponent

This component is responsible for defining the actual game effect.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `_tags`        | Tags associated with the effect, including `effect_protection`.             |
| `effect`       | Specifies the type of effect, which is `PROTECTION_EXPLOSION` in this case. |
| `frames`       | The duration of the effect. `-1` indicates it's a permanent or toggleable effect. |
| `exclusivity_group` | Groups effects that cannot be active simultaneously. `0` means it can stack with other effects in group 0. |

### InheritTransformComponent

This component is present but has no specific attributes configured, suggesting it inherits default transform properties.