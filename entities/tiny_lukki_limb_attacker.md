---
title: Tiny Lukki Limb Attacker
category: entities
---

# Tiny Lukki Limb Attacker

This entity defines a small, attacking limb for the Lukki creature in Noita. It's designed to be a component of a larger entity, likely contributing to the Lukki's movement and attack capabilities.

## Key Components

### IKLimbAttackerComponent
This component likely governs the attacking behavior of the limb.

*   **radius**: `14` - Defines the effective range or area of attack for this limb.

### IKLimbComponent
This component defines the physical properties of the limb.

*   **length**: `14` - Specifies the length of the limb.

### SpriteComponent (x2)
These components define the visual appearance of the limb. There are two separate `SpriteComponent` entries, suggesting the limb might have two distinct visual states or parts.

*   **image_file**:
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_A_tiny.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_B_tiny.png`
    These point to the image assets used for the limb's sprites.
*   **z_index**: `1.1` - Controls the layering of the sprite in the game world.
*   **offset_x**: `0` - Horizontal offset for the sprite.
*   **offset_y**: `5` - Vertical offset for the sprite.
*   **update_transform**: `0` - Indicates that the sprite's transform (position, rotation, scale) is not automatically updated by the game engine.
*   **update_transform_rotation**: `0` - Indicates that the sprite's rotation is not automatically updated.