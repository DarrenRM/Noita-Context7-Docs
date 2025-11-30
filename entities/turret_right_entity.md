---
title: Turret Right Entity
category: entities
---

# Turret Right Entity

This document describes the `turret_right.xml` entity, a variant of the standard turret found in Noita.

## Base Entity

The `turret_right.xml` entity inherits its base properties from `data/entities/animals/turret_right.xml`.

## Key Components

### DamageModelComponent

This component defines the health and knockback resistance of the turret.

| Attribute           | Value     | Description                                    |
| :------------------ | :-------- | :--------------------------------------------- |
| `hp`                | `9`       | Current health points.                         |
| `max_hp`            | `9`       | Maximum health points.                         |
| `minimum_knockback_force` | `100000`  | Minimum force required to knock back the entity. |

### Entity (Child)

This nested entity defines a special effect applied to the turret.

#### InheritTransformComponent

This component ensures the child entity inherits the transform (position, rotation, scale) of its parent.

#### GameEffectComponent

This component applies a game effect to the entity.

| Attribute | Value        | Description                                     |
| :-------- | :----------- | :---------------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | The game effect applied. In this case, immunity to freezing. |
| `frames`  | `-1`         | Duration of the effect. `-1` indicates permanent. |