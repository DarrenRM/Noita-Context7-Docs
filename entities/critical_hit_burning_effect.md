---
title: Critical Hit Burning Effect
category: entities
---

# Critical Hit Burning Effect

This entity defines a special hit effect that triggers when a critical hit occurs and the target is burning.

## HitEffectComponent

This component governs the behavior of the hit effect.

### Key Attributes:

*   **condition\_effect**: `ON_FIRE` - Specifies that this effect only applies if the target is currently burning.
*   **effect\_hit**: `CRITICAL_HIT_BOOST` - Indicates that this effect grants a boost when a critical hit is landed.
*   **value**: `100` - The magnitude of the critical hit boost.