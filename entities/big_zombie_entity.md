---
title: Big Zombie Entity
category: entities
---

# Big Zombie Entity

This document describes the `bigzombie.xml` entity, a variant of the standard zombie found in Noita.

## Core Attributes

The `bigzombie.xml` entity inherits its base properties from `data/entities/animals/bigzombie.xml`.

### Damage Component

This component defines the health and knockback resistance of the Big Zombie.

| Attribute             | Value       | Description                                     |
| :-------------------- | :---------- | :---------------------------------------------- |
| `hp`                  | `10`        | Current health points.                          |
| `max_hp`              | `10`        | Maximum health points.                          |
| `minimum_knockback_force` | `100000`    | Minimum force required to knock the entity back. |