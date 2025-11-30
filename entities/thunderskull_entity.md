---
title: Thunderskull Entity
category: entities
---

# Thunderskull Entity

This document describes the Thunderskull entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Entity Definition

The Thunderskull is a type of animal entity. Its core definition is inherited from `data/entities/animals/thunderskull.xml`.

## Key Components and Attributes

### DamageModelComponent

This component governs the Thunderskull's health and resistance to knockback.

| Attribute              | Value        | Description                                     |
| :--------------------- | :----------- | :---------------------------------------------- |
| `hp`                   | `6`          | Current health points.                          |
| `max_hp`               | `6`          | Maximum health points.                          |
| `minimum_knockback_force` | `100000`     | Minimum force required to cause knockback.      |

### Base Entity

The Thunderskull inherits its fundamental properties from a base entity definition.

```xml
<Base file="data/entities/animals/thunderskull.xml">
  <!-- ... other components ... -->
</Base>
```