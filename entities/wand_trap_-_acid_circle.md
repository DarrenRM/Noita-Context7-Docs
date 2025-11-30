---
title: Wand Trap - Acid Circle
category: entities
---

# Wand Trap - Acid Circle

This entity defines a "wand trap" that, when triggered, spawns an acid circle projectile.

## Key Attributes

*   **`tags`**: `wand_trap` - Identifies this entity as a wand trap.
*   **`VariableStorageComponent`**:
    *   **`name`**: `entity_file`
    *   **`value_string`**: `data/entities/projectiles/deck/circle_acid.xml` - Specifies the projectile entity to be spawned.

## Functionality

When a wand trap with these properties is activated (e.g., by proximity or a trigger), it will instantiate the `circle_acid.xml` projectile entity. This projectile is likely designed to create an area of effect damage or effect, in this case, acid.