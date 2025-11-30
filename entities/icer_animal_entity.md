---
title: Icer Animal Entity
category: entities
---

# Icer Animal Entity

This document describes the `icer.xml` entity, representing an "Icer" animal in Noita.

## Base Entity

The `icer.xml` entity inherits from a base `icer.xml` file, indicating it's a variation or extension of a pre-existing entity.

### Key Attributes

*   **DamageModelComponent**:
    *   `hp`: 6 (Hit Points)
    *   `max_hp`: 6 (Maximum Hit Points)
    *   `minimum_knockback_force`: 100000 (A very high value, suggesting significant resistance to knockback)

## Special Effects

The Icer entity possesses a special effect component.

### GameEffectComponent

*   `effect`: `PROTECTION_FREEZE` (Grants immunity or resistance to freezing effects)
*   `frames`: -1 (Indicates the effect is permanent or lasts indefinitely)