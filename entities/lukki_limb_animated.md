---
title: Lukki Limb Animated
category: entities
---

# Lukki Limb Animated

This entity defines an animated limb component for the Lukki creature. It utilizes multiple sprite components to create the visual effect of an animated limb, likely for its legs or feet.

## Key Components

### IKLimbComponent

This component is crucial for defining the kinematic properties of the limb.

*   **`length`**: Specifies the length of the limb.
    *   `40`: The default length of the limb.

### SpriteComponent

Multiple `SpriteComponent` instances are used to render different parts of the animated limb.

*   **`image_file`**: The path to the sprite image.
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_A.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_limb_B.png`
    *   `data/entities/animals/lukki/lukki_feet/lukki_knee.png`
*   **`z_index`**: Controls the rendering order of the sprite.
    *   `1.1`: Ensures the limb is rendered above other elements.
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `0` (for limb parts A and B)
    *   `4` (for the knee part)
*   **`offset_y`**: Vertical offset for the sprite.
    *   `5` (for limb parts A and B)
    *   `4` (for the knee part)
*   **`update_transform`**: Determines if the sprite's transform should be updated.
    *   `0`: Disables transform updates, likely for static sprite positioning relative to the limb's IK.
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   `0`: Disables rotation updates, likely for static sprite orientation relative to the limb's IK.

### InheritTransformComponent

This component is present but empty, suggesting it might be a placeholder or intended for future use where the entity inherits transform properties from a parent.