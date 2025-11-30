---
title: Lukki Limb Attacker (Long)
category: entities
---

# Lukki Limb Attacker (Long)

This entity defines a long attacking limb for the Lukki creature in Noita. It's primarily composed of visual components and an IK (Inverse Kinematics) limb attacker component.

## Key Components

### IKLimbAttackerComponent
This component enables the limb to act as an attacker within an IK system.

*   **radius**: `80` - The effective range or radius of the attacker.

### IKLimbComponent
This component defines the physical properties of the limb within an IK system.

*   **length**: `80` - The length of this specific limb segment.

### SpriteComponent
Multiple `SpriteComponent`s are used to define the visual appearance of the limb.

*   **image_file**: Specifies the texture file for the sprite.
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_A_long.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_B_long.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_knee.png`
*   **z_index**: `1.1` - Controls the drawing order of the sprite.
*   **offset_x**: `0` or `4` - Horizontal offset for the sprite.
*   **offset_y**: `5` or `4` - Vertical offset for the sprite.
*   **update_transform**: `0` - Indicates that the sprite's transform is not automatically updated.
*   **update_transform_rotation**: `0` - Indicates that the sprite's rotation is not automatically updated.

## Inheritance

*   **InheritTransformComponent**: This component is present but empty, suggesting it inherits transform properties from a parent entity.