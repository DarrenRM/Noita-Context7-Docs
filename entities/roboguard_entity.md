---
title: Roboguard Entity
category: entities
---

# Roboguard Entity

This document describes the `roboguard.xml` entity, a hostile creature found in Noita.

## Key Attributes

### DamageModelComponent
This component defines the roboguard's health and resistance to knockback.

| Attribute             | Value        | Description                                    |
| :-------------------- | :----------- | :--------------------------------------------- |
| `hp`                  | `13`         | Current health points.                         |
| `max_hp`              | `13`         | Maximum health points.                         |
| `minimum_knockback_force` | `100000`     | Minimum force required to knock the entity back. |

### GameEffectComponent
This component grants the roboguard a special effect.

| Attribute | Value   | Description                                    |
| :-------- | :------ | :--------------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | Grants immunity to freeze effects.             |
| `frames`  | `-1`    | Indicates the effect is permanent.             |