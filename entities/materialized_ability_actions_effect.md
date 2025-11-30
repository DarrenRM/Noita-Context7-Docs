---
title: Materialized Ability Actions Effect
category: entities
---

# Materialized Ability Actions Effect

This entity defines a special game effect that materializes ability actions.

## Key Components

### GameEffectComponent
This component is responsible for applying the core game effect.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `ABILITY_ACTIONS_MATERIALIZED` | Specifies the type of effect to be applied. |
| `frames` | `600` | The duration of the effect in frames (approximately 10 seconds). |

### InheritTransformComponent
This component is present but has no specific attributes configured, indicating it inherits default transform properties.