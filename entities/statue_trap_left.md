---
title: Statue Trap Left
category: entities
---

# Statue Trap Left

This entity represents the left-facing variant of a statue trap in Noita. It inherits its base functionality from `statue_trap_right.xml` and primarily defines its visual appearance.

## Key Attributes

*   **`name`**: `unknown` (This is a placeholder and might be intended to be more descriptive).
*   **`tags`**: `hittable`, `mortal`, `glue_NOT`
    *   `hittable`: The statue can be damaged.
    *   `mortal`: The statue can be destroyed.
    *   `glue_NOT`: The statue cannot be glued.

## Base Entity

*   **`file`**: `data/entities/buildings/statue_trap_right.xml`
    *   This indicates that `statue_trap_left.xml` inherits all properties and behaviors from the right-facing statue trap, with modifications specified within this file.

## Sprite Component

*   **`image_file`**: `data/buildings_gfx/statue_trap_left.xml`
    *   This attribute defines the graphical representation of the statue trap, specifically using the assets for the left-facing variant.