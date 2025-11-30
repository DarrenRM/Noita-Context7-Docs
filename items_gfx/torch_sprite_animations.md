---
title: Torch Sprite Animations
category: items_gfx
---

# Torch Sprite Animations

This document details the sprite animations for the torch item in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its default animation.

### Key Attributes:

*   **`filename`**: Specifies the path to the sprite sheet.
    *   `data/items_gfx/torch.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `6.5`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `10.0`
*   **`default_animation`**: The name of the animation to play by default.
    *   `default`

## Animation Definitions

The `<RectAnimation>` tags define individual animation sequences.

### `default` Animation

This is the primary animation for the torch.

*   **`name`**: `default`
*   **`pos_x`**: Starting X coordinate on the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y coordinate on the sprite sheet.
    *   `0`
*   **`frame_count`**: Total number of frames in this animation.
    *   `4`
*   **`frame_width`**: Width of each individual frame.
    *   `12`
*   **`frame_height`**: Height of each individual frame.
    *   `12`
*   **`frame_wait`**: Delay between frames in seconds.
    *   `0.09`
*   **`frames_per_row`**: Number of frames in a single row of the sprite sheet.
    *   `4`
*   **`loop`**: Whether the animation should loop. `1` for true, `0` for false.
    *   `1`

### `out` Animation

This animation likely represents the torch being extinguished.

*   **`name`**: `out`
*   **`pos_x`**: `0`
*   **`pos_y`**: `12` (Starts on the second row of the sprite sheet)
*   **`frame_count`**: `1`
*   **`frame_width`**: `12`
*   **`frame_height`**: `12`
*   **`frame_wait`**: `0.09`
*   **`frames_per_row`**: `4`
*   **`loop`**: `1`

### `appear` Animation

This animation likely represents the torch being lit or appearing.

*   **`name`**: `appear`
*   **`pos_x`**: `0`
*   **`pos_y`**: `24` (Starts on the third row of the sprite sheet)
*   **`frame_count`**: `5`
*   **`frame_width`**: `12`
*   **`frame_height`**: `12`
*   **`frame_wait`**: `0.05`
*   **`frames_per_row`**: `5`
*   **`loop`**: `0` (Does not loop)

### `disappear` Animation

This animation likely represents the torch fading away or being put out.

*   **`name`**: `disappear`
*   **`pos_x`**: `0`
*   **`pos_y`**: `36` (Starts on the fourth row of the sprite sheet)
*   **`frame_count`**: `3`
*   **`frame_width`**: `12`
*   **`frame_height`**: `12`
*   **`frame_wait`**: `0.05`
*   **`frames_per_row`**: `3`
*   **`loop`**: `0` (Does not loop)