---
title: Temple Rubble 03 Prop
category: entities
---

---

# Temple Rubble 03 Prop

This entity defines a piece of rubble found in the temple environment. It's a physics-based prop with a visual representation.

## Key Attributes

*   **`name`**: `unknown` (This is a placeholder and might be better defined for clarity in a mod.)
*   **`Base file`**: `data/entities/base_item_physics2.xml`
    *   This indicates the entity inherits physics properties and behaviors from a base physics item.

### `PhysicsBody2Component`

This component governs the physical behavior of the rubble.

*   **`init_offset_y`**: `3.5`
    *   Specifies an initial vertical offset for the physics body.

### `PhysicsImageShapeComponent`

This component defines the visual shape and material properties of the rubble.

*   **`image_file`**: `data/props_gfx/temple_rubble_03.png`
    *   The graphical asset used for this rubble.
*   **`material`**: `rock_box2d`
    *   The physics material applied, likely defining its density, friction, and collision properties.