---
title: Fireball Ray Enemy Hit Effect
category: entities
---

# Fireball Ray Enemy Hit Effect

This entity defines the visual and functional effect that occurs when an enemy is hit by a fireball ray.

## Key Components

### HitEffectComponent
This component dictates what happens when the entity is hit.

*   **`effect_hit`**: Specifies the type of effect to trigger.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: Indicates that a unique child entity should be loaded as the hit effect.
*   **`value_string`**: The path to the entity that will be loaded as the hit effect.
    *   `data/entities/misc/fireball_ray_enemy.xml`: This points to the entity responsible for the actual fireball ray effect on the enemy.