---
title: Lava Trail Effect Entity
category: entities
---

# Lava Trail Effect Entity

This entity defines a projectile that leaves a trail of lava.

## Key Components

### ShotEffectComponent

This component dictates the visual and functional effects applied to a projectile.

| Attribute        | Description                                     |
|------------------|-------------------------------------------------|
| `extra_modifier` | Specifies the visual effect to be applied.      |
| `projectile_lava_trail` | This value indicates the lava trail effect. |

### LifetimeComponent

This component controls how long the entity persists.

| Attribute | Description                               |
|-----------|-------------------------------------------|
| `lifetime` | The duration in frames the entity exists. |
| `1800`    | The lava trail will last for 1800 frames. |