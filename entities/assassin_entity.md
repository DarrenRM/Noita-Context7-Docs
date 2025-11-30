---
title: Assassin Entity
category: entities
---

# Assassin Entity

This document describes the `assassin.xml` entity, a variant of the base assassin enemy in Noita.

## Key Attributes

The `assassin.xml` entity inherits from `data/entities/animals/assassin.xml` and modifies specific components.

### DamageModelComponent

*   **hp**: 18 (Hit Points)
*   **max_hp**: 18 (Maximum Hit Points)
*   **minimum_knockback_force**: 100000 (A very high value, indicating strong resistance to knockback)

### Additional Components

This entity includes two additional nested entities:

1.  **Energy Shield Sector**:
    *   Inherits from `data/entities/misc/animal_energy_shield_sector.xml`. This likely provides a defensive shield mechanism.

2.  **Protection Component**:
    *   **effect**: `PROTECTION_FREEZE` (Grants immunity to freezing effects)
    *   **frames**: -1 (Indicates the protection is permanent)