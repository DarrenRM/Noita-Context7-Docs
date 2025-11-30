---
title: Curse Wither Projectile Hit Effect
category: entities
---

# Curse Wither Projectile Hit Effect

This entity defines the visual and functional effect when a "curse wither" projectile hits a target.

## Key Components

### HitEffectComponent

This component dictates what happens when the projectile makes contact.

*   **`effect_hit`**: Specifies the type of effect to trigger.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: Indicates that a new, unique entity will be spawned at the hit location.
*   **`value_string`**: Defines the entity to be loaded as the hit effect.
    *   `data/entities/misc/curse_wither_projectile.xml`: This points to the entity that will be instantiated upon impact, likely containing the visual and behavioral elements of the curse wither effect.