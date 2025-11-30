---
title: Slime Giga Explosion Hit Effect
category: entities
---

# Slime Giga Explosion Hit Effect

This entity defines a special hit effect that triggers when an entity with the "SLIMY" status condition is hit.

## Key Components

### HitEffectComponent

This component governs the behavior when a specific condition is met.

*   **`condition_status`**: `SLIMY` - The effect is triggered when the target entity has the "SLIMY" status.
*   **`effect_hit`**: `LOAD_UNIQUE_CHILD_ENTITY` - When triggered, this effect loads a unique child entity.
*   **`value_string`**: `data/entities/misc/hitfx_explode_explosion_giga.xml` - Specifies the entity to be loaded as the child effect, which in this case is a "Giga Explosion" effect.

## Summary

When an entity afflicted with the "SLIMY" status is hit, it will trigger a "Giga Explosion" effect, as defined by the `hitfx_explode_explosion_giga.xml` entity. This is a common way to create visually impactful reactions to specific status effects in Noita.