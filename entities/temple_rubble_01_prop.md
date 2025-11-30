---
title: Temple Rubble 01 Prop
category: entities
---

---

# Temple Rubble 01 Prop

This entity defines a piece of rubble found in the temples of Noita. It's a physics-based prop with a visual representation.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits core physics and item functionalities from a base entity.

### PhysicsBody2Component

*   **`init_offset_y="4.5"`**:  Specifies an initial vertical offset for the physics body.

### PhysicsImageShapeComponent

*   **`image_file="data/props_gfx/temple_rubble_01.png"`**:  Defines the visual sprite for the rubble.
*   **`material="rock_box2d"`**:  Assigns a physics material, likely influencing its interaction with other physics objects (e.g., friction, density).