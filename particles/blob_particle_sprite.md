---
title: Blob Particle Sprite
category: particles
---

# Blob Particle Sprite

This document describes the sprite definition for the "blob" particle in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/particles/blob.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `4`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `4`
*   **`default_animation`**: The name of the animation to play by default.
    *   `stand`

## Animation: `stand`

The `RectAnimation` element defines a rectangular animation sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `stand`
*   **`pos_x`**: Starting X position within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual frame.
    *   `8`
*   **`frame_height`**: The height of each individual frame.
    *   `8`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
    *   `0.07`
*   **`frames_per_row`**: The number of frames in a single row of the sprite sheet.
    *   `6`
*   **`loop`**: Whether the animation should loop.
    *   `1` (true)