---
title: Fly Nest Sprite
category: data/buildings_gfx
---

---

# Fly Nest Sprite

This document describes the sprite definition for the "Fly Nest" building in Noita, focusing on its visual representation and animation.

## Sprite Definition

The primary sprite for the Fly Nest is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/buildings_gfx/flynest.png` - Specifies the image file used for the sprite.
*   **offset_x**: `14` - Horizontal offset of the sprite's origin.
*   **offset_y**: `26` - Vertical offset of the sprite's origin.
*   **default_animation**: `stand` - The animation that plays by default when the sprite is active.

## Animation: "stand"

The "stand" animation defines the visual sequence for the Fly Nest.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `28` - The width of each individual frame.
*   **frame_height**: `28` - The height of each individual frame.
*   **frame_wait**: `0.15` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).