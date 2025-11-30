---
title: Orb 09 Sprite and Animation
category: items_gfx
---

```

# Orb 09 Sprite and Animation

This document details the sprite and animation data for Orb 09 in Noita.

## Sprite Data

The primary sprite for Orb 09 is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_09.png` - Specifies the image file used for the sprite.
*   **offset_x**: `20` - Horizontal offset for the sprite's position.
*   **offset_y**: `48` - Vertical offset for the sprite's position.
*   **default_animation**: `default` - Links to the default animation sequence.

## Animation Data

The animation for Orb 09 is defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `default` - The name of this animation sequence.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `7` - The total number of frames in the animation.
*   **frame_width**: `40` - The width of each individual animation frame.
*   **frame_height**: `50` - The height of each individual animation frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop continuously (1 for true, 0 for false).