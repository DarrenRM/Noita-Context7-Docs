---
title: Temple Rubble 04 Prop
category: entities
---

# Temple Rubble 04 Prop

This entity represents a piece of rubble found in the temple environment. It's a physics-enabled prop with a visual representation.

## Key Components

### Base Entity

*   **`base_item_physics2.xml`**: Inherits physics properties and behaviors from a base physics item.

### Physics Body

*   **`PhysicsBody2Component`**:
    *   `init_offset_y`: Controls the initial vertical offset of the physics body.

### Physics Shape

*   **`PhysicsImageShapeComponent`**: Defines the physical shape and visual appearance of the rubble.
    *   `image_file`: Specifies the texture file for the rubble (`data/props_gfx/temple_rubble_04.png`).
    *   `material`: Sets the physics material to `rock_box2d`, influencing its interaction with other physics objects.