---
title: Effect Stun Protection Electricity
category: entities
---

# Effect Stun Protection Electricity

This entity defines a temporary status effect that grants protection against electrical stun.

## Key Components

### GameEffectComponent
This component manages the core functionality of the game effect.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `STUN_PROTECTION_ELECTRICITY` | Specifies the type of effect being applied. |
| `frames` | `7200` | The duration of the effect in game frames (approximately 2 minutes). |

### InheritTransformComponent
This component is present but has no configurable attributes in this specific entity, indicating it inherits standard transform properties.