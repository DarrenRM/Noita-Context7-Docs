---
title: Lukki Limb Entity
category: entities
---

# Lukki Limb Entity

This entity defines a single limb for a Lukki creature in Noita. It primarily handles the visual representation and basic kinematic properties of the limb.

## Key Components and Attributes

### `IKLimbComponent`

This component is essential for defining the limb's physical properties and how it interacts with the IK (Inverse Kinematics) system.

*   **`length`**: (float) The length of the limb segment. In this case, it's set to `40`.

### `SpriteComponent`

Multiple `SpriteComponent`s are used to define the visual appearance of the limb, including different parts like the main limb segments and the knee joint.

*   **`image_file`**: (string) Path to the image file for the sprite.
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_A.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_B.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_knee.png`
*   **`z_index`**: (float) Controls the rendering order of the sprite. A value of `1.1` suggests it's rendered slightly above other base elements.
*   **`offset_x`**, **`offset_y`**: (float) Adjusts the sprite's position relative to its parent entity.
*   **`update_transform`**: (0 or 1) Determines if the sprite's transform (position, rotation, scale) should be updated automatically. Set to `0` here, meaning manual updates are expected or not needed for this sprite.
*   **`update_transform_rotation`**: (0 or 1) Similar to `update_transform`, but specifically for rotation. Set to `0` here.

### `InheritTransformComponent`

This component, when present, allows the entity to inherit transform properties from its parent. In this case, it's empty, suggesting it might not be actively inheriting or its default behavior is sufficient.

### `IKLimbWalkerComponent`

This component is likely responsible for the limb's walking or movement logic within the IK system. Its presence indicates this limb is designed to be part of a walking animation or system. The component itself has no configurable attributes in this definition.