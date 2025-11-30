---
title: Tentacler Entity
category: entities
---

# Tentacler Entity

This document describes the `tentacler.xml` entity, a creature found in Noita. It's a relatively simple entity primarily defined by its health and its constituent tentacle parts.

## Key Attributes

### DamageModelComponent
This component defines the tentacler's health and resistance to knockback.

| Attribute        | Value   | Description                               |
| :--------------- | :------ | :---------------------------------------- |
| `hp`             | `15`    | Current health points.                    |
| `max_hp`         | `15`    | Maximum health points.                    |
| `minimum_knockback_force` | `100000` | Minimum force required to knock it back. |

### Base Entity
The tentacler inherits its core properties from a base `tentacler.xml` file, suggesting a common template for this type of creature.

### Tentacle Components
The tentacler is composed of multiple tentacle entities, each defined by its own XML file and positioned relative to the main tentacler entity.

| Tentacle File                                    | Relative Position (x, y) |
| :----------------------------------------------- | :----------------------- |
| `data/entities/verlet_chains/smalltentacle/tentacler_tentacle_01.xml` | (-4, -2)                 |
| `data/entities/verlet_chains/smalltentacle/tentacler_tentacle_01.xml` | (4, 1)                   |
| `data/entities/verlet_chains/smalltentacle/tentacler_tentacle_02.xml` | (0, -1)                  |

These tentacle entities likely handle the visual appearance and potentially the attack mechanics of the tentacler. The `InheritTransformComponent` and `Transform` tags indicate how these parts are attached and oriented.