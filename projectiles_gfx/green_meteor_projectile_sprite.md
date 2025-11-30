---
title: Green Meteor Projectile Sprite
category: projectiles_gfx
---

---

# Green Meteor Projectile Sprite

This document describes the sprite and animation data for the "green meteor" projectile in Noita.

## Sprite Definition

The primary sprite for the green meteor is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/meteor_green.png` - Specifies the image file used for the sprite.
*   **offset_x**: `12` - Horizontal offset of the sprite's origin.
*   **offset_y**: `12` - Vertical offset of the sprite's origin.
*   **default_animation**: `default` - The name of the animation to play by default.

## Animation Definition

The projectile uses a rectangular animation for its visual effect.

### Key Attributes for `RectAnimation` (name="default"):

*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `24` - The width of each individual animation frame.
*   **frame_height**: `24` - The height of each individual animation frame.
*   **frame_wait**: `0.09` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).