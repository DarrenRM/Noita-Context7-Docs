---
title: Nest Emissive Alternate Sprite
category: buildings_gfx
---

# Nest Emissive Alternate Sprite

This document describes the `nest_emissive_alt.xml` file, which defines an alternate sprite for a "nest" building in Noita, focusing on its visual appearance and animation.

## Sprite Definition

The primary `<Sprite>` element defines the base image and animation properties.

### Key Attributes:

*   **filename**: `data/buildings_gfx/nest_emissive_alt.png` - Specifies the image file used for this sprite.
*   **offset_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset_y**: `32` - The vertical offset of the sprite's origin.
*   **default_animation**: `"stand"` - The animation that plays by default when the sprite is active.

## Animation: "stand"

The `<RectAnimation>` element defines the "stand" animation.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `32` - The width of each individual frame.
*   **frame_height**: `32` - The height of each individual frame.
*   **frame_wait**: `0.15` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).