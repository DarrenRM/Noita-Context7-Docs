---
title: Slime Hit Effect Explosion
category: entities
---

# Slime Hit Effect Explosion

This entity defines a special hit effect that triggers when an entity with the "SLIMY" status condition is hit.

## HitEffectComponent

This component governs the behavior when a specific condition is met.

### Key Attributes:

*   `condition_status`: Specifies the status condition that must be present for the effect to trigger. In this case, it's `"SLIMY"`.
*   `effect_hit`: Determines the type of effect to apply. `"LOAD_UNIQUE_CHILD_ENTITY"` means a unique child entity will be loaded.
*   `value_string`: The path to the entity to be loaded as the child entity. Here, it's `"data/entities/misc/hitfx_explode_explosion.xml"`, indicating a standard explosion effect.