---
title: Lightning Ray Enemy Hit Effect
category: entities
---

# Lightning Ray Enemy Hit Effect

This entity defines the visual and functional effect that occurs when an enemy is hit by a lightning ray.

## Key Components

### HitEffectComponent

This component dictates what happens when the entity is hit.

*   **`effect_hit`**: Specifies the type of effect to trigger.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: Indicates that a unique child entity should be loaded as the hit effect.
*   **`value_string`**: Defines the path to the entity that will be loaded as the hit effect.
    *   `data/entities/misc/lightning_ray_enemy.xml`: This is the specific entity loaded, which likely contains the visual and behavioral elements of the lightning ray impact.

## Summary

The `hitfx_lightning_ray_enemy.xml` file is a simple entity that acts as a trigger. When this entity is "hit" (likely by another game mechanic), it instructs the game to load a specific child entity (`lightning_ray_enemy.xml`) to represent the actual impact effect of a lightning ray on an enemy. This is a common pattern for decoupling hit effects from the entities that cause them.