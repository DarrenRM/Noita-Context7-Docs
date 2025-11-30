---
title: Critical Hit Blood Effect
category: entities
---

# Critical Hit Blood Effect

This entity defines a special hit effect that triggers when a critical hit occurs, applying a "BLOODY" condition and boosting damage.

## Key Components

### HitEffectComponent

This component governs the effects that occur when an entity is hit.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `condition_effect`  | The status effect to apply. `BLOODY` in this case.                          |
| `effect_hit`        | The type of hit effect. `CRITICAL_HIT_BOOST` indicates a critical hit bonus. |
| `value`             | The magnitude of the effect. `100` suggests a significant boost.            |