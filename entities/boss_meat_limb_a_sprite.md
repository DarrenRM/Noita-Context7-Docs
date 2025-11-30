---
title: Boss Meat Limb A Sprite
category: entities
---

---

# Boss Meat Limb A Sprite

This document describes the sprite data for the "Boss Meat Limb A" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_meat/limb_a.png` - Specifies the image file used for the sprite.
*   **offset_x**: `0` - Horizontal offset of the sprite.
*   **offset_y**: `4` - Vertical offset of the sprite.
*   **default_animation**: `stand` - The animation that plays by default when the entity is spawned.

## Animations

### `stand` Animation

This animation defines the "stand" state for the limb.

#### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `26` - The width of each individual frame.
*   **frame_height**: `5` - The height of each individual frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).