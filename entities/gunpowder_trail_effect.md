---
title: Gunpowder Trail Effect
category: entities
---

# Gunpowder Trail Effect

This entity defines a visual effect that trails behind a projectile, specifically for gunpowder-related projectiles.

## Key Components

### ShotEffectComponent
This component dictates the type of effect applied to the projectile.

*   **`extra_modifier`**: `projectile_gunpowder_trail` - This is the crucial identifier that links this entity to the gunpowder trail visual effect.

### LifetimeComponent
This component determines how long the effect persists.

*   **`lifetime`**: `2400` - The duration of the effect in game frames.