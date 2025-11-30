---
title: All Protection Effect Entity
category: entities
---

# All Protection Effect Entity

This entity defines a game effect that grants the player complete protection against all damage types.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `effect`  | Specifies the type of effect to apply.    |
| `frames`  | Duration of the effect in game frames.    |

**Key Attributes:**

*   `effect`: `PROTECTION_ALL` - This is the core attribute that defines the effect as granting complete protection.
*   `frames`: `1800` - The effect will last for 1800 game frames (approximately 30 seconds at 60 FPS).

### InheritTransformComponent

This component is present but has no specific attributes defined, indicating it inherits default transform properties.