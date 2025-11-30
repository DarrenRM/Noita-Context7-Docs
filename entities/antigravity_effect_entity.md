---
title: Antigravity Effect Entity
category: entities
---

# Antigravity Effect Entity

This entity defines an effect that applies antigravity to entities it interacts with.

## Key Components

### `ShotEffectComponent`

This component is responsible for applying the effect.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `extra_modifier` | Specifies the type of effect to apply. In this case, it's `"antigravity"`. |

### `LifetimeComponent`

This component determines how long the effect persists.

| Attribute | Description                                                               |
|-----------|---------------------------------------------------------------------------|
| `lifetime`  | The duration of the effect in frames. `3600` frames is equivalent to 60 seconds. |