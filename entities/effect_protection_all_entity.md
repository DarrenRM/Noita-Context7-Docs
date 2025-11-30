---
title: Effect Protection All Entity
category: entities
---

# Effect Protection All Entity

This entity defines a game effect that grants the player complete protection against all damage types.

## Key Components

### `GameEffectComponent`

This component is responsible for defining the specific game effect applied.

*   **`_tags`**: `effect_protection_all` - Identifies this specific effect.
*   **`effect`**: `PROTECTION_ALL` - Specifies the type of effect, granting immunity to all damage.
*   **`frames`**: `7200` - The duration of the effect in game frames (approximately 2 minutes).

### `InheritTransformComponent`

This component indicates that the entity inherits its transform properties, likely meaning it doesn't have unique positional or rotational data and is primarily defined by its effect.