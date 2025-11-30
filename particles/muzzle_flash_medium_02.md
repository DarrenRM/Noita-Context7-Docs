---
title: Muzzle Flash Medium 02
category: particles
---

# Muzzle Flash Medium 02

This document describes the configuration for a muzzle flash particle effect in Noita, specifically `muzzle_medium_02.xml`.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_medium_02.png` - Specifies the image file used for the sprite.
*   **offset_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset_y**: `7` - The vertical offset of the sprite's origin.
*   **default_animation**: `muzzle` - The name of the default animation to play.

## Animation Configuration

The animation for this muzzle flash is defined using the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by the `<Sprite>` tag.
*   **pos_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual animation frame.
*   **frame_height**: `16` - The height of each individual animation frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).