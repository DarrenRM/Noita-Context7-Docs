---
title: Extra Money Trick Kill Effect
category: entities
---

# Extra Money Trick Kill Effect

This entity defines a game effect that grants the player extra money when a specific "trick kill" condition is met.

## Key Components

### GameEffectComponent
This component is responsible for applying the game effect.

*   **`effect`**: `EXTRA_MONEY_TRICK_KILL` - Specifies the type of effect.
*   **`frames`**: `600` - The duration (in frames) for which this effect is active.

## Inheritance

### InheritTransformComponent
This component indicates that the entity inherits transform properties, meaning its position, rotation, and scale are managed by its parent or the game's transform system. In this case, it's an empty tag, suggesting no specific transform modifications are applied directly within this entity.