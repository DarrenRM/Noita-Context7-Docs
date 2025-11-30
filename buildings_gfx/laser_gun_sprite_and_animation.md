---
title: Laser Gun Sprite and Animation
category: buildings_gfx
---

---

# Laser Gun Sprite and Animation

This document describes the sprite and animation data for the "lasergun" building in Noita.

## Sprite Definition

The primary sprite for the lasergun is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/buildings_gfx/lasergun.png` - Specifies the image file used for the sprite.
*   **offset_x**: `6` - Horizontal offset of the sprite's origin.
*   **offset_y**: `6` - Vertical offset of the sprite's origin.
*   **default_animation**: `"stand"` - The animation that plays by default when the building is idle.

## Animation: "stand"

The "stand" animation defines the visual sequence for the lasergun when it is not actively performing an action.

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos_x**: `"0"` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos_y**: `"0"` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame_count**: `8` - The total number of frames in this animation.
*   **frame_width**: `12` - The width of each individual animation frame.
*   **frame_height**: `12` - The height of each individual animation frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `8` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).