---
title: Gravity Effect Entity
category: entities
---

# Gravity Effect Entity

This entity defines a projectile effect that modifies gravity.

## Key Components

### ShotEffectComponent

This component is responsible for applying the effect to a projectile.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `extra_modifier` | Specifies the type of effect to apply. Set to `"gravity"` to apply a gravity modification. |

### LifetimeComponent

Determines how long the effect persists.

| Attribute | Description                                     |
|-----------|-------------------------------------------------|
| `lifetime`  | The duration of the effect in seconds.          |