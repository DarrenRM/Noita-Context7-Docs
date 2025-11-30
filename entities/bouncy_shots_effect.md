---
title: Bouncy Shots Effect
category: entities
---

# Bouncy Shots Effect

This entity defines a projectile effect that causes shots to bounce.

## Key Components

### ShotEffectComponent

This component is responsible for applying the "bounce" effect to projectiles.

*   **`extra_modifier`**: Set to `"bounce"` to enable the bouncing behavior.

### LifetimeComponent

Determines how long the effect persists.

*   **`lifetime`**: The duration in seconds the effect is active. In this case, it's set to `3600` seconds (1 hour).

## Inheritance

*   **`InheritTransformComponent`**: This component is present but has no specific attributes defined, indicating it inherits default transform properties.