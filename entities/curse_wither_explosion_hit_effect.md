---
title: Curse Wither Explosion Hit Effect
category: entities
---

# Curse Wither Explosion Hit Effect

This entity defines a hit effect that triggers a specific explosion when applied.

## Key Components

### HitEffectComponent

This component dictates what happens when the entity is hit.

*   **`effect_hit`**: Specifies the type of effect to apply.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: Indicates that a unique child entity should be loaded.
*   **`value_string`**: The path to the entity that will be loaded as the child effect.
    *   `data/entities/misc/curse_wither_explosion.xml`: This is the specific entity that will be instantiated upon being hit.

```xml
<Entity>
    <HitEffectComponent
        effect_hit="LOAD_UNIQUE_CHILD_ENTITY"
        value_string="data/entities/misc/curse_wither_explosion.xml">
    </HitEffectComponent>
</Entity>
```