---
title: Poison Trail Effect Entity
category: entities
---

# Poison Trail Effect Entity

This entity defines a projectile effect that leaves a trail of poison.

## Key Components

### `ShotEffectComponent`

This component is responsible for applying the effect to a projectile.

*   **`extra_modifier`**: `projectile_poison_trail` - This is the core identifier for the poison trail effect.

### `LifetimeComponent`

Determines how long the effect persists.

*   **`lifetime`**: `1800` - The duration of the effect in game frames.