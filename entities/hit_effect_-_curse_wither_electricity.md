---
title: Hit Effect - Curse Wither Electricity
category: entities
---

# Hit Effect - Curse Wither Electricity

This entity defines a hit effect that triggers when a projectile or other damaging entity makes contact. It specifically loads another entity to apply a "curse wither electricity" effect.

## Key Components

### HitEffectComponent

This is the primary component responsible for defining the hit effect.

*   **`effect_hit`**: Specifies the type of effect to apply.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: Indicates that a new entity will be loaded and instantiated at the hit location.
*   **`value_string`**: The path to the entity that will be loaded and applied as the hit effect.
    *   `data/entities/misc/curse_wither_electricity.xml`: This is the specific entity loaded, which likely contains the visual and functional aspects of the curse wither electricity effect.