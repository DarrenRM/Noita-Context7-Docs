---
title: Skullfly Entity
category: entities
---

# Skullfly Entity

This document describes the `skullfly.xml` entity, a common enemy found in the Crypt biome.

## Key Attributes

### DamageModelComponent

This component defines the combat-related properties of the Skullfly.

| Attribute                 | Value        | Description                                     |
| :------------------------ | :----------- | :---------------------------------------------- |
| `hp`                      | `14.6`       | Current health points.                          |
| `max_hp`                  | `14.6`       | Maximum health points.                          |
| `minimum_knockback_force` | `100000`     | The minimum force required to knock back the entity. This high value suggests it's resistant to being pushed. |

### Base Entity

The Skullfly inherits its base properties from a generic `data/entities/animals/skullfly.xml` file, indicating it's a standard animal entity with specific modifications.