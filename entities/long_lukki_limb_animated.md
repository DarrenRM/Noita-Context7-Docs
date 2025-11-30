---
title: Long Lukki Limb (Animated)
category: entities
---

# Long Lukki Limb (Animated)

This entity defines a single, animated limb for the Lukki creature in Noita. It utilizes multiple `SpriteComponent`s to create the visual appearance of a segmented limb, likely for animation purposes.

## Key Components

### `IKLimbComponent`

This component is crucial for defining the limb's physical properties and how it interacts within an Inverse Kinematics (IK) system.

*   **`length`**: `80` - Specifies the total length of the limb.

### `SpriteComponent`

Multiple `SpriteComponent`s are used to render the different parts of the limb.

*   **`image_file`**:
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_A_long.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_B_long.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_knee.png`
    These define the visual assets for the limb segments and the knee joint.
*   **`z_index`**: `1.1` - Controls the rendering order of the sprites, ensuring they appear correctly layered.
*   **`offset_x`**, **`offset_y`**: These attributes define the sprite's position relative to its parent entity's origin.
    *   Limb A/B: `offset_x="0"`, `offset_y="5"`
    *   Knee: `offset_x="4"`, `offset_y="4"`
*   **`update_transform`**: `0` - Indicates that the sprite's transform (position, rotation, scale) is not automatically updated by the engine.
*   **`update_transform_rotation`**: `0` - Similar to `update_transform`, this prevents automatic rotation updates.

## Summary

This entity is a building block for the Lukki's animated legs. It leverages the `IKLimbComponent` for its functional behavior and multiple `SpriteComponent`s for its visual representation, allowing for complex limb animations.