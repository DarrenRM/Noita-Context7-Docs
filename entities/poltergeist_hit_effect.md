---
title: Poltergeist Hit Effect
category: entities
---

# Poltergeist Hit Effect

This entity defines a special hit effect that triggers when something is hit.

## HitEffectComponent

This component governs how the entity reacts to being hit.

### Key Attributes:

*   **`effect_hit`**: Specifies the type of effect to apply. In this case, `LOAD_ENTITY` means another entity will be loaded.
*   **`value_string`**: The path to the entity to be loaded when this hit effect is triggered. Here, it points to `data/entities/misc/physics_poltergeist_ai.xml`, which likely spawns a poltergeist AI entity.