---
title: Orb 04 Sprite Animation
category: items_gfx
---

```

# Orb 04 Sprite Animation

This document details the sprite and animation data for "orb_04" in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for orb_04 is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_04.png` - Specifies the image file used for the sprite.
*   **offset_x**: `20` - Horizontal offset of the sprite's origin.
*   **offset_y**: `48` - Vertical offset of the sprite's origin.
*   **default_animation**: `default` - Links to the default animation sequence.

## Animation Data

The animation for orb_04 is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `default` - The identifier for this animation sequence.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `7` - The total number of frames in the animation.
*   **frame_width**: `40` - The width of each individual animation frame.
*   **frame_height**: `50` - The height of each individual animation frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).

This data can be used to programmatically control or modify the visual behavior of orb_04 within the game.