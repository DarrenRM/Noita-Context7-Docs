---
title: Spearbot Entity
category: entities
---

# Spearbot Entity

This document describes the `spearbot.xml` entity, a variant of the base `spearbot` found in Noita.

## Base Entity

The `spearbot.xml` inherits its core properties from `data/entities/animals/spearbot.xml`.

## Key Attributes

### DamageModelComponent

This component defines the combat statistics for the Spearbot.

| Attribute           | Value     | Description                                  |
| :------------------ | :-------- | :------------------------------------------- |
| `hp`                | `50`      | Current health points.                       |
| `max_hp`            | `50`      | Maximum health points.                       |
| `minimum_knockback_force` | `100000` | Minimum force required to knock the entity back. |

### GameEffectComponent (Freeze Protection)

This entity grants the Spearbot immunity to freezing effects.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | Specifies the type of protection.         |
| `frames`  | `-1`  | Indicates permanent protection (infinite frames). |

### GameEffectComponent (Explosion Protection)

This entity also grants the Spearbot immunity to explosion damage.

| Attribute | Value              | Description                                  |
| :-------- | :----------------- | :------------------------------------------- |
| `effect`  | `PROTECTION_EXPLOSION` | Specifies the type of protection.            |
| `frames`  | `-1`               | Indicates permanent protection (infinite frames). |