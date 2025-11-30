---
title: Temple Rubble 02 Prop
category: entities
---

# Temple Rubble 02 Prop

This entity represents a piece of rubble found in the temple environment. It's a physics-based prop with a visual representation.

## Key Components

### Base Entity
*   **Base file:** `data/entities/base_item_physics2.xml` - Inherits physics and item-related functionalities.

### Physics Body
*   **`PhysicsBody2Component`**:
    *   `init_offset_y`: `5.5` - Specifies an initial vertical offset for the physics body.

### Physics Image Shape
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/props_gfx/temple_rubble_02.png` - The graphical asset used for this prop.
    *   `material`: `rock_box2d` - Defines the physical material properties, influencing interactions like friction and collision.