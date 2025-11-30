---
title: Fire Trail Effect Entity
category: entities
---

# Fire Trail Effect Entity

This entity defines a visual effect that leaves a trail of fire behind a projectile.

## Key Components

### `ShotEffectComponent`

This component is responsible for applying the visual effect to the projectile.

*   **`extra_modifier`**: Specifies the type of effect to apply. In this case, `"projectile_fire_trail"` indicates a fire trail.

### `LifetimeComponent`

This component determines how long the effect persists.

*   **`lifetime`**: The duration of the effect in game frames. A value of `2400` means the trail will last for 2400 frames.