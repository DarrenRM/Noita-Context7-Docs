---
title: Alcohol Trail Effect Entity
category: entities
---

# Alcohol Trail Effect Entity

This entity defines a projectile effect that leaves an alcohol trail.

## Key Components

### `ShotEffectComponent`

This component dictates the visual and functional effects applied to a projectile.

*   **`extra_modifier`**: `projectile_alcohol_trail` - This is the core identifier for the alcohol trail effect.

### `LifetimeComponent`

This component determines how long the effect persists.

*   **`lifetime`**: `2400` - The duration of the effect in game frames.