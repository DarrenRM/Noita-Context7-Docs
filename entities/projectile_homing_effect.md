---
title: Projectile Homing Effect
category: entities
---

# Projectile Homing Effect

This entity defines a projectile that exhibits homing behavior.

## Key Components

### GameEffectComponent

This component is responsible for applying the homing effect to the projectile.

*   **`effect`**: `PROJECTILE_HOMING` - Specifies the type of game effect.
*   **`frames`**: `600` - The duration in frames for which the homing effect will persist.

## Usage

This entity is typically used as a component within a projectile entity to give it the ability to track and follow targets.