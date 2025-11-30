---
title: Monk Entity
category: entities
---

# Monk Entity

This document describes the Monk entity in Noita, focusing on its key attributes for AI-assisted modding.

## Base Entity

The Monk entity inherits its base properties from `data/entities/animals/monk.xml`.

## Damage Component

### DamageModelComponent

This component defines the Monk's health and resistance to damage.

| Attribute           | Value       | Description                                      |
| :------------------ | :---------- | :----------------------------------------------- |
| `hp`                | `15`        | Current health points.                           |
| `max_hp`            | `15`        | Maximum health points.                           |
| `minimum_knockback_force` | `100000`    | Minimum force required to knock the Monk back. |

#### Damage Multipliers

| Damage Type | Multiplier | Description                                     |
| :---------- | :--------- | :---------------------------------------------- |
| `projectile`| `0.0`      | The Monk is immune to projectile damage.        |

## Special Effects

### GameEffectComponent

This component applies special effects to the entity.

| Attribute | Value | Description                                  |
| :-------- | :---- | :------------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | Grants immunity to freezing effects. |
| `frames`  | `-1`  | The effect is permanent (lasts indefinitely). |