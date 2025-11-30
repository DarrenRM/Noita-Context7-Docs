---
title: Projectile Homing Perk
category: scripts/perks
---

---

# Projectile Homing Perk

This script defines a perk that grants projectiles a homing capability. When a projectile with this perk is fired, it gains a `HomingComponent`.

## Key Components

### `HomingComponent`

This component is added to projectiles to enable homing behavior.

*   **`homing_targeting_coeff`**: Controls how strongly the projectile targets its enemy. A higher value means more aggressive targeting.
    *   **Value**: `130.0`
*   **`homing_velocity_multiplier`**: Adjusts the projectile's velocity while homing. A value less than 1.0 will slow it down.
    *   **Value**: `0.86`

## Functionality

The `shot` function is triggered when a projectile is fired. It checks if the entity has a `ProjectileComponent` and, if so, adds the `HomingComponent` with the specified parameters.