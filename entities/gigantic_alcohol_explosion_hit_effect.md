---
title: Gigantic Alcohol Explosion Hit Effect
category: entities
---

# Gigantic Alcohol Explosion Hit Effect

This entity defines a special hit effect that triggers when an entity with the "ALCOHOLIC" status condition is hit.

## Key Components

### HitEffectComponent

This component governs the effect that occurs when the entity is hit.

*   **`condition_status`**: Specifies the status condition that must be met for the effect to trigger.
    *   `ALCOHOLIC`: The effect will activate if the target entity has the "ALCOHOLIC" status.
*   **`effect_hit`**: Determines the type of effect to apply.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: This indicates that a unique child entity will be loaded and spawned as the hit effect.
*   **`value_string`**: The path to the entity that will be loaded as the hit effect.
    *   `data/entities/misc/hitfx_explode_explosion_giga.xml`: This points to a pre-defined "gigantic explosion" entity, which will be spawned when the condition is met.

This setup allows for a visually impactful explosion to occur specifically when an "alcoholic" entity is damaged.