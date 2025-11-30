---
title: Flamer Entity Configuration
category: entities
---

# Flamer Entity Configuration

This document details the configuration for the "Flamer" entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Entity Structure

The Flamer entity inherits its base properties from `data/entities/animals/flamer.xml`.

## Key Components and Attributes

### DamageModelComponent

This component defines the Flamer's health and resistance to knockback.

| Attribute                 | Value        | Description                                       |
| :------------------------ | :----------- | :------------------------------------------------ |
| `hp`                      | `6`          | Current health points.                            |
| `max_hp`                  | `6`          | Maximum health points.                            |
| `minimum_knockback_force` | `100000`     | Minimum force required to knock the entity back. |

---
SKIP