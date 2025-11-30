---
title: Quantum FX Blue Sprite
category: projectiles_gfx
---

# Quantum FX Blue Sprite

This document describes the sprite definition for the "Quantum FX Blue" projectile effect in Noita. It details the visual appearance and animation of this projectile.

## Sprite Definition

The main `Sprite` element defines the base image and its positioning.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. Here, it's set to `"fireball"`.
*   **`filename`**: The path to the image file used for the sprite.
    *   `data/projectiles_gfx/quantum_fx_blue.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `8`

## Animation: `fireball`

The `RectAnimation` element defines the specific animation sequence.

### Key Attributes:

*   **`name`**: The name of this animation, matching `default_animation`.
    *   `"fireball"`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual frame.
    *   `17`
*   **`frame_height`**: The height of each individual frame.
    *   `17`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.06`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `7`
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel.
    *   `1` (True)