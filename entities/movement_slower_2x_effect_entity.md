---
title: Movement Slower 2x Effect Entity
category: entities
---

# Movement Slower 2x Effect Entity

This entity defines a game effect that slows down the player's movement by a factor of 2.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `MOVEMENT_SLOWER_2X` | Specifies the type of game effect to apply. |
| `frames` | `600` | The duration of the effect in game frames (approximately 10 seconds). |

### InheritTransformComponent

This component is present but has no configurable attributes in this specific entity, indicating it inherits standard transform properties.