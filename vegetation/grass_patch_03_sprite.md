---
title: Grass Patch 03 Sprite
category: data
---

# Grass Patch 03 Sprite

This documentation describes the sprite definition for `grass_patch_03.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary element is the `<Sprite>` tag, which defines the visual representation of the grass patch.

### Key Attributes

*   **`filename`**: Specifies the image file used for the sprite.
    *   `data/vegetation/grass_patch_03.png`
*   **`offset_x`**: Horizontal offset for the sprite's position.
    *   `10`
*   **`offset_y`**: Vertical offset for the sprite's position.
    *   `9`
*   **`default_animation`**: The animation to play by default.
    *   `vegetation_growth` (This is a special animation name that triggers a growing vegetation effect.)

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes

*   **`name`**: The name of the animation.
    *   `vegetation_growth`
*   **`pos_x`**, **`pos_y`**: Starting position of the animation frames within the sprite sheet.
    *   `0`, `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `1`
*   **`frame_width`**: The width of each individual frame.
    *   `20`
*   **`frame_height`**: The height of each individual frame.
    *   `10`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `1.0`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `1`
*   **`loop`**: Determines if the animation should loop.
    *   `1` (Loops indefinitely)