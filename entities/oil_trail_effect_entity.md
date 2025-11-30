---
title: Oil Trail Effect Entity
category: entities
---

# Oil Trail Effect Entity

This entity defines a projectile effect that leaves an oil trail.

## Key Components

### ShotEffectComponent

This component dictates the visual and functional effect applied to a projectile.

*   **`extra_modifier`**: `projectile_oil_trail` - This is the core identifier for the oil trail effect.

### LifetimeComponent

This component controls how long the effect persists.

*   **`lifetime`**: `2400` - The duration of the oil trail effect in game frames.