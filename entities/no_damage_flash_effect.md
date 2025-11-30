---
title: No Damage Flash Effect
category: entities
---

---

# No Damage Flash Effect

This entity defines a visual effect that indicates the player is immune to damage for a short period.

## Entity Structure

The entity is composed of the following key components:

*   **`InheritTransformComponent`**: This component is present but has no specific attributes defined, indicating it inherits its transform properties from its parent or context.
*   **`GameEffectComponent`**: This is the core component responsible for the effect's behavior.

### `GameEffectComponent` Attributes

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `effect`  | Specifies the type of game effect. In this case, it's `NO_DAMAGE_FLASH`. |
| `frames`  | The duration of the effect in frames. `600` frames is approximately 10 seconds (at 60 FPS). |