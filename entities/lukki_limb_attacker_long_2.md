---
title: Lukki Limb Attacker Long 2
category: entities
---

# Lukki Limb Attacker Long 2

This entity defines a specific limb component for a Lukki creature in Noita, designed for attacking. It utilizes an Inverse Kinematics (IK) system for limb control.

## Key Components

### `IKLimbAttackerComponent`

This component enables the limb to act as an attacker.

*   **`radius`**: `80` - The effective range or radius of the limb's attack.

### `IKLimbComponent`

This component defines the physical properties of the IK limb.

*   **`length`**: `80` - The length of the limb segment.

### `SpriteComponent`

This entity uses multiple `SpriteComponent`s to render different parts of the limb.

*   **`image_file`**: Specifies the texture file for each sprite.
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_A_long2.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_B_long2.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_knee2.png`
*   **`z_index`**: `1.1` - Controls the rendering order of the sprites.
*   **`offset_x`**, **`offset_y`**: Adjusts the position of the sprite relative to its parent.
*   **`update_transform`**: `0` - Indicates that the sprite's transform is not automatically updated by the IK system.
*   **`update_transform_rotation`**: `0` - Indicates that the sprite's rotation is not automatically updated by the IK system.