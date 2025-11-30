---
title: Green Orb Projectile
category: entities
---

# Green Orb Projectile

This document details the configuration of the "Green Orb" projectile entity in Noita, primarily focusing on its visual, physical, and behavioral attributes for AI-assisted modding.

## Core Entity Configuration

The projectile is based on `data/entities/base_projectile.xml`, inheriting fundamental projectile properties.

### Base Projectile Properties

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `gravity_y`     | `0`   | No vertical gravity applied to the projectile.                              |
| `air_friction`  | `0`   | No air resistance affecting the projectile's movement.                      |
| `mass`          | `0.06`| A small mass value, influencing its interaction with physics.               |

## Projectile Component

This component defines the projectile's core behavior, including its trajectory, damage, and death effects.

### Key Projectile Attributes

| Attribute                   | Value                                                              | Description