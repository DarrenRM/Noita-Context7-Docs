---
title: Large Pink Muzzle Flash 01
category: particles
---

# Large Pink Muzzle Flash 01

This documentation describes the particle effect for a large pink muzzle flash, commonly used in Noita for weapon firing.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   `filename`: Specifies the texture file used for the sprite.
    *   `data/particles/muzzle_flashes/muzzle_large_pink_01.png`
*   `offset_x`: Horizontal offset of the sprite's origin.
    *   `8`
*   `offset_y`: Vertical offset of the sprite's origin.
    *   `7`
*   `default_animation`: The name of the animation to use by default.
    *   `muzzle`

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   `name`: The name of this animation, referenced by `default_animation`.
    *   `muzzle`
*   `pos_x`: X-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `0`
*   `pos_y`: Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `0`
*   `frame_count`: The total number of frames in the animation.
    *   `1`
*   `frame_width`: The width of each animation frame.
    *   `16`
*   `frame_height`: The height of each animation frame.
    *   `16`
*   `frame_wait`: The duration (in seconds) each frame is displayed.
    *   `0.1`
*   `frames_per_row`: The number of frames in a single row of the sprite sheet.
    *   `1`
*   `loop`: Whether the animation should loop. `0` indicates no loop.
    *   `0`