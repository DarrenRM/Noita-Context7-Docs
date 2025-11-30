---
title: Temple Rubble 05 Prop
category: entities
---

# Temple Rubble 05 Prop

This entity represents a piece of rubble found in the temple environment. It's a physics-enabled prop with a visual representation.

## Key Attributes

*   **`name`**: `unknown` (This is a placeholder and might be intended to be more descriptive).
*   **`Base file`**: `data/entities/base_item_physics2.xml` - Inherits physics properties and behaviors from a base physics item.

### `PhysicsBody2Component`

This component defines the physical properties of the rubble.

*   **`init_offset_y`**: `4.5` - An initial vertical offset for the physics body.

### `PhysicsImageShapeComponent`

This component defines the visual shape and material of the rubble.

*   **`image_file`**: `data/props_gfx/temple_rubble_05.png` - Specifies the image asset used for the rubble's appearance.
*   **`material`**: `rock_box2d` - Defines the physical material properties, likely influencing its interaction with other physics objects.