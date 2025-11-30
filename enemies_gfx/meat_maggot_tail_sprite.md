---
title: Meat Maggot Tail Sprite
category: enemies_gfx
---

---

# Meat Maggot Tail Sprite

This document describes the sprite definition for the "meatmaggot_tail" enemy in Noita.

## Sprite Definition

The primary `<Sprite>` element defines the visual representation and animation for the meat maggot's tail.

### Key Attributes:

*   **filename**: `data/enemies_gfx/meatmaggot_tail.png` - Specifies the image file used for the sprite.
*   **offset_x**: `9` - Horizontal offset of the sprite's origin.
*   **offset_y**: `4.5` - Vertical offset of the sprite's origin.
*   **default_animation**: `stand` - The animation to play by default when the sprite is active.

## Animation: "stand"

The `<RectAnimation>` element defines the "stand" animation.

### Key Attributes:

*   **name**: `stand` - The name of this specific animation.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `10` - The width of each individual frame in pixels.
*   **frame_height**: `9` - The height of each individual frame in pixels.
*   **frames_per_row**: `1` - How many frames are arranged horizontally in the sprite sheet.
*   **frame_wait**: `0.082` - The duration (in seconds) each frame is displayed before advancing.
*   **pos_x**: `0` - The X-coordinate of the top-left corner of the animation's frame within the sprite sheet.
*   **pos_y**: `0` - The Y-coordinate of the top-left corner of the animation's frame within the sprite sheet.