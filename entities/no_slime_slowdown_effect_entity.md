---
title: No Slime Slowdown Effect Entity
category: entities
---

# No Slime Slowdown Effect Entity

This entity defines a game effect that prevents the player from being slowed down by slime.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `NO_SLIME_SLOWDOWN`.
*   **`frames`**: The duration of the effect in game frames. `720` frames is equivalent to 12 seconds (720 frames / 60 frames per second).

### InheritTransformComponent

This component is present but has no specific configurations, indicating it inherits default transform properties.

## Usage

This entity is likely used to create temporary power-ups or environmental effects that grant immunity to slime's slowing properties.