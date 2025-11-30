---
title: Drone Lasership Entity
category: entities
---

---

# Drone Lasership Entity

This document describes the `drone_lasership.xml` entity, a type of drone found in Noita.

## Key Attributes

### Base Entity Properties

*   **`file`**: `data/entities/animals/drone_lasership.xml` - Specifies the base file for this entity.
*   **`include_children`**: `1` - Indicates that child entities should be included.

### Damage Component

*   **`DamageModelComponent`**: Manages the entity's health and damage resistance.
    *   **`hp`**: `13` - The current health points of the drone.
    *   **`max_hp`**: `13` - The maximum health points of the drone.
    *   **`minimum_knockback_force`**: `100000` - A very high value, suggesting strong resistance to knockback.
    *   **`damage_multipliers`**:
        *   **`projectile`**: `0.0` - The drone takes no damage from projectiles.

### Special Effects

*   **`GameEffectComponent`**: Applies special effects to the entity.
    *   **`effect`**: `PROTECTION_FREEZE` - Grants immunity to freezing.
    *   **`frames`**: `-1` - The freeze protection effect is permanent (lasts indefinitely).