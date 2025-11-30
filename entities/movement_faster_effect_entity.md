---
title: Movement Faster Effect Entity
category: entities
---

---

# Movement Faster Effect Entity

This entity defines a game effect that increases the player's movement speed.

## Entity Definition

The core of this entity is the `GameEffectComponent`.

### GameEffectComponent

This component applies a specific game effect to the entity.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of game effect to apply.               |
| `frames`  | The duration of the effect in game frames.      |

**Key Attributes:**

*   **`effect`**: Set to `MOVEMENT_FASTER` to indicate the speed increase.
*   **`frames`**: Determines how long the movement speed buff lasts. A value of `1800` means the effect will persist for 1800 game frames.

## Inheritance

*   **`InheritTransformComponent`**: This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transform properties.