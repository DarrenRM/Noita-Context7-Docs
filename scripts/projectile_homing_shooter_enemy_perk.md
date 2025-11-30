---
title: Projectile Homing Shooter Enemy Perk
category: scripts
---

# Projectile Homing Shooter Enemy Perk

This script defines a perk that grants enemies a homing projectile ability. When an enemy with this perk fires a projectile, it gains a `HomingComponent`.

## Key Components

### `shot` Function

This function is called when an entity with this perk fires a projectile. It checks if the entity has a `ProjectileComponent` and, if so, adds a `HomingComponent` to it.

### `HomingComponent` Attributes

The `HomingComponent` is added with the following key attributes:

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `target_who_shot`         | Specifies the target for the homing projectile. `"1"` typically means the player. |
| `homing_targeting_coeff`  | Controls how strongly the projectile targets its destination. Higher values mean more aggressive targeting. |
| `homing_velocity_multiplier` | Adjusts the projectile's velocity when homing. A value of `0.99` slightly reduces its speed. |
| `detect_distance`         | The distance at which the projectile will begin to actively home in on its target. |