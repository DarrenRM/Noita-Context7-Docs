---
title: Wizard Teleporter Entity
category: entities
---

# Wizard Teleporter Entity

This document describes the `wizard_tele.xml` entity, a variant of the teleporter wizard found in Noita.

## Key Attributes

### DamageModelComponent

This component defines the health and resilience of the wizard.

| Attribute             | Value        | Description                                  |
| :-------------------- | :----------- | :------------------------------------------- |
| `hp`                  | `14`         | Current health points.                       |
| `max_hp`              | `14`         | Maximum health points.                       |
| `minimum_knockback_force` | `100000`     | Minimum force required to knock back the entity. |

### Entity: cape

This nested entity defines the visual appearance and physics of the wizard's cape.

#### Base: cape.xml

References the base definition for the cape.

#### VerletPhysicsComponent

Defines the physics properties of the cape.

| Attribute       | Value      | Description                                  |
| :-------------- | :--------- | :------------------------------------------- |
| `cloth_color_edge` | `0xFFC4B37E` | The color of the cape's edge (RGBA hex).     |
| `cloth_color`   | `0xFF40572B` | The main color of the cape (RGBA hex).       |