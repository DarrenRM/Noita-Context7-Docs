---
title: Worm Tiny Tail Sprite
category: entities
---

---

# Worm Tiny Tail Sprite

This document describes the sprite definition for the "worm_tiny_tail" enemy in Noita.

## Sprite Definition

The primary sprite for the worm's tiny tail segment is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_tiny_tail.png` - Specifies the image file used for this sprite.
*   **offset_x**: `9` - Horizontal offset for the sprite's anchor point.
*   **offset_y**: `4.5` - Vertical offset for the sprite's anchor point.
*   **default_animation**: `stand` - The animation that plays by default when the sprite is active.

## Animations

The sprite includes a single animation named "stand".

### Stand Animation Details:

*   **name**: `stand`
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_height**: `9` - The height of each individual frame in pixels.
*   **frame_wait**: `0.082` - The duration (in seconds) each frame is displayed before advancing.
*   **frame_width**: `10` - The width of each individual frame in pixels.
*   **frames_per_row**: `1` - How many frames are arranged horizontally in the sprite sheet.
*   **pos_x**: `0` - The X-coordinate of the top-left corner of the animation's frame within the sprite sheet.
*   **pos_y**: `0` - The Y-coordinate of the top-left corner of the animation's frame within the sprite sheet.