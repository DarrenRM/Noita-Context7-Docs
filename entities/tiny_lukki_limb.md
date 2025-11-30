---
title: Tiny Lukki Limb
category: entities
---

---

# Tiny Lukki Limb

This entity defines a small limb component for the Lukki creature. It's primarily used for its leg structure.

## Key Components

### SpriteComponent
This component handles the visual representation of the limb.

*   **image_file**: Specifies the image file for the limb. There are two `SpriteComponent`s, likely for different parts or states of the limb.
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_A_tiny.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_B_tiny.png`
*   **z_index**: Controls the drawing order of the sprite. A value of `1.1` suggests it's drawn above other elements.
*   **offset_x**, **offset_y**: Adjusts the sprite's position relative to its parent entity.
*   **update_transform**, **update_transform_rotation**: Set to `0`, meaning the sprite's transform (position, rotation) is not automatically updated by the game engine based on the entity's transform.

### IKLimbComponent
This component defines the physical properties of an Inverse Kinematics (IK) limb.

*   **length**: The length of the limb segment. Here, it's set to `14`.

### IKLimbWalkerComponent
This component enables IK limb functionality for walking or movement. Its presence indicates this limb is part of a walking mechanism.

### InheritTransformComponent
This component, when present, allows the entity to inherit the transform (position, rotation, scale) of its parent. In this case, it's empty, suggesting it might not be actively inheriting or its default behavior is sufficient.