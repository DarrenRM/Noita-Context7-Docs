---
title: High Spread Shot Effect
category: entities/
---

# High Spread Shot Effect

This entity defines a projectile that has an "extreme spread" modifier applied to its shot. This is typically used for effects that cause projectiles to scatter widely.

## Key Components

### ShotEffectComponent

This component is responsible for applying various effects to a projectile.

*   **`extra_modifier`**: Specifies the type of spread. In this case, `"extreme_spread"` is used, indicating a significant scattering of projectiles.

### LifetimeComponent

This component determines how long the entity persists.

*   **`lifetime`**: The duration in seconds the entity will exist. Here, it's set to `3600` seconds (1 hour).

## Inherited Components

*   **`InheritTransformComponent`**: This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transform properties.