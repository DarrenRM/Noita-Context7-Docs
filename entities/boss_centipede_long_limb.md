---
title: Boss Centipede Long Limb
category: entities
---

# Boss Centipede Long Limb

This entity defines a long limb segment for the boss centipede. It's designed to be part of a larger, articulated creature, utilizing IK (Inverse Kinematics) for movement.

## Key Components

### InheritTransformComponent
*   This component indicates that the entity inherits its transform properties (position, rotation, scale) from its parent.

### IKLimbWalkerComponent
*   **`ground_attachment_min_spread`**: `80` - Defines the minimum spread distance for the limb when attaching to the ground.
*   **`_tags="disabled_at_start"`**: This tag suggests the limb might be disabled initially and activated later in the game.

### IKLimbComponent
*   **`length`**: `160` - Specifies the length of this limb segment.

### SpriteComponent (Multiple)

This entity uses multiple `SpriteComponent`s to render different parts of the limb.

*   **Limb Segment A:**
    *   **`image_file`**: `data/entities/animals/boss_centipede/limbs/limb_long_A.xml` - The primary sprite for the limb segment.
    *   **`z_index`**: `1.2` - Controls the drawing order, placing this sprite above others with lower `z_index`.
    *   **`offset_x`, `offset_y`**: `0`, `8` - Adjusts the sprite's position relative to the entity's origin.
    *   **`update_transform`, `update_transform_rotation`**: `0` - Disables automatic transform updates for the sprite, likely controlled by IK.
    *   **`rect_animation`, `next_rect_animation`**: `stand` - Specifies the current and next animation state for the sprite.

*   **Limb Segment B:**
    *   **`image_file`**: `data/entities/animals/boss_centipede/limbs/limb_long_B.xml` - A secondary sprite for the limb segment, potentially for variation or detail.
    *   **`z_index`**: `1.2`
    *   **`offset_x`, `offset_y`**: `0`, `8`
    *   **`update_transform`, `update_transform_rotation`**: `0`
    *   **`rect_animation`, `next_rect_animation`**: `stand`

*   **Knee Joint Sprite:**
    *   **`image_file`**: `data/entities/animals/boss_centipede/limbs/limb_long_knee.xml` - Sprite for the knee joint.
    *   **`z_index`**: `1.1` - Drawn slightly behind the main limb segments.
    *   **`offset_x`, `offset_y`**: `8`, `8`
    *   **`update_transform`, `update_transform_rotation`**: `0`