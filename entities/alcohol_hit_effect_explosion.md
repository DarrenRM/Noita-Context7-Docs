---
title: Alcohol Hit Effect Explosion
category: entities
---

# Alcohol Hit Effect Explosion

This entity defines a special hit effect that triggers when an entity with the "ALCOHOLIC" status condition is hit.

## HitEffectComponent

This component governs the effect that occurs when the entity is hit.

### Key Attributes:

*   **`condition_status`**: Specifies the status condition that must be present for this effect to trigger. In this case, it's `"ALCOHOLIC"`.
*   **`effect_hit`**: Determines the type of effect to apply. Here, it's set to `"LOAD_UNIQUE_CHILD_ENTITY"`, meaning a specific child entity will be loaded.
*   **`value_string`**: The path to the entity that will be loaded as the child entity when the effect is triggered. It points to `"data/entities/misc/hitfx_explode_explosion.xml"`, which is a generic explosion effect.

This setup effectively makes entities with the "ALCOHOLIC" status explode with a standard explosion effect when damaged.