---
title: Missile Crab Entity
category: entities
---

---

# Missile Crab Entity

This document describes the Missile Crab entity in Noita, focusing on its key attributes for AI-assisted modding.

## Base Entity

The Missile Crab inherits its base properties from `data/entities/animals/missilecrab.xml`.

## Key Components

### DamageModelComponent

This component defines the combat statistics of the Missile Crab.

| Attribute              | Value        | Description                                     |
| :--------------------- | :----------- | :---------------------------------------------- |
| `hp`                   | `22.5`       | Current health points.                          |
| `max_hp`               | `22.5`       | Maximum health points.                          |
| `minimum_knockback_force` | `100000`     | Minimum force required to knock the entity back. |

### GameEffectComponent

This component applies a specific game effect to the entity.

| Attribute | Value   | Description                                     |
| :-------- | :------ | :---------------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | The entity is protected from freezing.          |
| `frames`  | `-1`    | The effect lasts indefinitely (until removed). |