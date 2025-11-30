---
title: Wizard Returner Entity
category: entities
---

---

# Wizard Returner Entity

This document describes the `wizard_returner.xml` entity, a hostile creature found in the crypt.

## Core Attributes

*   **`DamageModelComponent`**:
    *   `hp`: 19 (Hit Points)
    *   `max_hp`: 19 (Maximum Hit Points)
    *   `minimum_knockback_force`: 100000 (High value indicates significant resistance to knockback)

## Special Effects

*   **`GameEffectComponent`**:
    *   `effect`: `PROTECTION_EXPLOSION` (Grants immunity or resistance to explosions)
    *   `frames`: -1 (Indicates the effect is permanent or lasts indefinitely)

## Visual Components

*   **`Entity name="cape"`**:
    *   This entity attaches a `cape.xml` component, likely a visual element.
    *   **`VerletPhysicsComponent`**:
        *   `cloth_color_edge`: `0xFFbafcff` (Edge color of the cloth)
        *   `cloth_color`: `0xFF384d6b` (Main color of the cloth)