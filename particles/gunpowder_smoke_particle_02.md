---
title: Gunpowder Smoke Particle 02
category: particles
---

# Gunpowder Smoke Particle 02

This document describes the configuration for a specific gunpowder smoke particle effect in Noita, designed for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `"explosion"`
*   **`filename`**: The path to the sprite sheet containing the particle's frames.
    *   Value: `"data/particles/smoke_gunpowder_02.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"10"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"10"`
*   **`rect_animation`**: Links to a `RectAnimation` definition.
    *   Value: `"explosion"`

## RectAnimation Configuration

The `RectAnimation` element details how the sprite sheet is used to create an animated sequence.

### Key Attributes:

*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"9"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `"0.06"`
*   **`frame_height`**: The height of a single frame in pixels.
    *   Value: `"20"`
*   **`frame_width`**: The width of a single frame in pixels.
    *   Value: `"20"`
*   **`frames_per_row`**: The number of frames arranged horizontally on the sprite sheet.
    *   Value: `"12"`
*   **`loop`**: Determines if the animation should loop.
    *   Value: `"0"` (0 indicates no looping)
*   **`name`**: The name of this specific rectangle animation, referenced by the `Sprite`.
    *   Value: `"explosion"`
*   **`pos_x`**: The X-coordinate of the top-left corner of the animation's frame area on the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The Y-coordinate of the top-left corner of the animation's frame area on the sprite sheet.
    *   Value: `"0"`