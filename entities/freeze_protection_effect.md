---
title: Freeze Protection Effect
category: entities
---

# Freeze Protection Effect

This entity defines a game effect that grants the player protection against freezing.

## Key Components

### `GameEffectComponent`

This component manages the game effect itself.

*   **`effect`**: Specifies the type of effect. In this case, it's `PROTECTION_FREEZE`, indicating protection against freezing.
*   **`frames`**: Determines the duration of the effect in game frames. `7200` frames is equivalent to 2 minutes (7200 frames / 60 frames per second = 120 seconds).

### `InheritTransformComponent`

This component is present but has no specific configurations, suggesting it inherits default transform properties.