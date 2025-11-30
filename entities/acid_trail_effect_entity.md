---
title: Acid Trail Effect Entity
category: entities
---

# Acid Trail Effect Entity

This entity defines the visual and functional aspects of an acid trail effect in Noita, typically applied to projectiles.

## Core Components

### `ShotEffectComponent`

This component is crucial for defining the effect applied by a projectile.

| Attribute         | Description                                                                 |
| :---------------- | :-------------------------------------------------------------------------- |
| `extra_modifier`  | Specifies the modifier to be applied, in this case, `projectile_acid_trail`. |

### `LifetimeComponent`

Determines how long the acid trail effect persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration of the effect in frames.     |
|           | `1800` frames (approximately 30 seconds). |

## Inheritance

### `InheritTransformComponent`

This component indicates that the entity inherits transformation properties (position, rotation, scale) from its parent or the entity it's attached to. This is standard for effects that follow projectiles.