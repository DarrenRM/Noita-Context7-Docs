---
title: Tank Entity
category: entities
---

---

# Tank Entity

This document describes the `tank.xml` entity, a type of animal found in Noita.

## Key Attributes

### Base Entity

*   **`file`**: `data/entities/animals/tank.xml` - Inherits base properties from the `tank.xml` entity.

### DamageModelComponent

*   **`hp`**: `13.5` - The current health points of the tank.
*   **`max_hp`**: `13.5` - The maximum health points of the tank.
*   **`minimum_knockback_force`**: `100000` - A very high value indicating significant resistance to knockback.

### GameEffectComponent

This component grants the tank a special effect.

*   **`effect`**: `PROTECTION_FREEZE` - The tank is immune to freezing effects.
*   **`frames`**: `-1` - The freeze protection is permanent (lasts indefinitely).