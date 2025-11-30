---
title: Treble Eye Particle Sprite
category: particles
---

# Treble Eye Particle Sprite

This document describes the sprite definition for the "treble_eye" particle in Noita. It details the visual appearance and animation of this particle.

## Sprite Definition

The primary sprite definition is enclosed within the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the image file used for the sprite.
    *   `data/particles/treble_eye.png`
*   **`default_animation`**: Sets the animation to play by default when the particle is created.
    *   `blink`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `32`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `16`

## Animation: `blink`

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `blink`
*   **`frame_count`**: The total number of frames in the animation.
    *   `19`
*   **`frame_width`**: The width of each individual frame.
    *   `64`
*   **`frame_height`**: The height of each individual frame.
    *   `32`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `19`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.1`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   `0`
*   **`shrink_by_one_pixel`**: Whether each frame should shrink by one pixel after each loop (not applicable here as `loop` is `0`).
    *   `0`