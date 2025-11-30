---
title: Boss Limb Attacker Entity
category: entities
---

# Boss Limb Attacker Entity

This entity defines a component of a boss's limb that is capable of attacking. It utilizes several components to define its visual representation and its attacking behavior.

## Key Components

### `IKLimbAttackerComponent`

This component defines the attacking capabilities of the limb.

*   **`radius`**: The range at which the limb can attack.

### `IKLimbComponent`

This component defines the physical properties of the limb.

*   **`length`**: The length of the limb segment.

### `SpriteComponent`

This component defines the visual appearance of the limb. Multiple `SpriteComponent`s are used to assemble the limb from different image parts.

*   **`image_file`**: The path to the sprite image.
    *   `data/entities/animals/boss_limbs/limb1_A.png`
    *   `data/entities/animals/boss_limbs/limb1_B.png`
    *   `data/entities/animals/boss_limbs/knee.png`
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.
*   **`update_transform`**: Whether the sprite's transform should be updated. Set to `0` (false) for static sprites.
*   **`update_transform_rotation`**: Whether the sprite's rotation should be updated. Set to `0` (false) for static sprites.
*   **`z_index`**: Determines the rendering order of the sprite. Higher values are rendered on top.