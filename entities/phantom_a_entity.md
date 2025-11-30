---
title: Phantom A Entity
category: entities
---

---

# Phantom A Entity

This document describes the `phantom_a.xml` entity, a type of phantom found in the crypt biome.

## Key Attributes

### DamageModelComponent
This component defines the combat properties of the Phantom A.

| Attribute             | Value        | Description                                      |
| :-------------------- | :----------- | :----------------------------------------------- |
| `hp`                  | 12           | Current health points.                           |
| `max_hp`              | 12           | Maximum health points.                           |
| `minimum_knockback_force` | 100000       | Minimum force required to knock back the entity. |

### GameEffectComponent
This component applies a persistent game effect to the entity.

| Attribute | Value   | Description                                      |
| :-------- | :------ | :----------------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | The game effect applied (immunity to freeze). |
| `frames`  | -1      | Duration of the effect (infinite in this case).  |

## Inheritance

The entity inherits base properties from `data/entities/animals/phantom_a.xml`.

## Transform

The `InheritTransformComponent` indicates that this entity inherits its transformation properties from its parent.