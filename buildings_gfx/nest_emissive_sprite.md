---
title: Nest Emissive Sprite
category: data/buildings_gfx
---

---

# Nest Emissive Sprite

This document describes the sprite definition for the "nest_emissive" building graphic in Noita. It details the visual appearance and animation of this building element.

## Sprite Definition

The primary sprite definition is enclosed within the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/buildings_gfx/nest_emissive.png` - Specifies the image file used for the sprite.
*   **offset_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset_y**: `32` - The vertical offset of the sprite's origin.
*   **default_animation**: `stand` - The animation that plays by default when the sprite is active.

## Animation: "stand"

The `<RectAnimation>` tag defines the "stand" animation.

### Key Attributes:

*   **name**: `stand` - The name of this specific animation.
*   **pos_x**: `0` - The starting X-coordinate within the sprite sheet for this animation.
*   **pos_y**: `0` - The starting Y-coordinate within the sprite sheet for this animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `32` - The width of each individual frame in pixels.
*   **frame_height**: `32` - The height of each individual frame in pixels.
*   **frame_wait**: `0.15` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).