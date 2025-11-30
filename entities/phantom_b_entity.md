---
title: Phantom B Entity
category: entities
---

# Phantom B Entity

This document describes the `phantom_b.xml` entity, a type of enemy found in the crypt biome.

## Key Attributes

### DamageModelComponent
*   **hp**: 12 (Hit Points)
*   **max_hp**: 12 (Maximum Hit Points)
*   **minimum_knockback_force**: 100000 (A very high value, suggesting it's resistant to being knocked back)

### GameEffectComponent
*   **effect**: `PROTECTION_FREEZE` (This entity is immune to freeze effects)
*   **frames**: -1 (Indicates the effect is permanent)

## Inheritance

This entity inherits its base properties from `data/entities/animals/phantom_b.xml`.

## Notes for Modding

*   The high `minimum_knockback_force` indicates this entity is designed to be difficult to displace.
*   The `PROTECTION_FREEZE` with `-1` frames means it will never be frozen.
*   This entity appears to be a basic variant of a phantom enemy with specific defensive properties.