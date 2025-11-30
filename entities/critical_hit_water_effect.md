---
title: Critical Hit Water Effect
category: entities
---

# Critical Hit Water Effect

This entity defines a special hit effect that triggers when an entity is hit while in water.

## HitEffectComponent

This component governs the conditions and effects of a hit.

### Key Attributes:

*   **`condition_effect`**: Specifies the condition that must be met for the effect to trigger. In this case, it's `"WET"`, meaning the target must be wet.
*   **`effect_hit`**: Defines the type of effect to apply when the condition is met. Here, it's `"CRITICAL_HIT_BOOST"`, indicating an enhancement to critical hits.
*   **`value`**: A numerical value associated with the effect. A value of `"100"` suggests a significant boost.