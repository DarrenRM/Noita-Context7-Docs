---
title: Effect Trail - Water
category: entities
---

# Effect Trail - Water

This entity defines a visual effect that trails behind projectiles, specifically for water-related effects.

## Key Components

### ShotEffectComponent

This component dictates the visual effect applied to a projectile.

*   **`extra_modifier`**: `projectile_water_trail` - This is the crucial identifier that links this entity to the specific water trail visual effect.

### LifetimeComponent

This component controls how long the effect persists.

*   **`lifetime`**: `2400` - The duration of the effect in game frames.