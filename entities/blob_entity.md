---
title: Blob Entity
category: entities
---

# Blob Entity

This document describes the `blob.xml` entity, a basic enemy type in Noita.

## Key Attributes

### DamageModelComponent

This component defines the health and knockback resistance of the blob.

| Attribute              | Value        | Description                                     |
| :--------------------- | :----------- | :---------------------------------------------- |
| `hp`                   | `4.5`        | Current health points.                          |
| `max_hp`               | `4.5`        | Maximum health points.                          |
| `minimum_knockback_force` | `100000`     | Minimum force required to knock the entity back. |

## Base Entity

The blob inherits its base properties from `data/entities/animals/blob.xml`. This implies it shares fundamental behaviors and visual elements with other entities defined in that base file.

## AI and Behavior

While not explicitly detailed in this snippet, the `Base file` attribute suggests that the blob's AI, movement, and attack patterns are defined in its parent entity file. For more detailed information on its behavior, refer to the `blob.xml` file within the `data/entities/animals/` directory.