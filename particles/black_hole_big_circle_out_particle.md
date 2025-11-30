---
title: Black Hole Big Circle Out Particle
category: particles
---

# Black Hole Big Circle Out Particle

This document describes the `black_hole_big_circle_out.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play, which is "explosion" in this case.
*   **`filename`**: The image file used for the sprite.
    *   `data/particles/black_hole_big_circle_out.png`
*   **`offset_x`**: Horizontal offset of the sprite.
    *   `67`
*   **`offset_y`**: Vertical offset of the sprite.
    *   `67`

## Animation: "explosion"

The "explosion" animation defines how the sprite animates.

### Key Attributes:

*   **`name`**: The name of the animation.
    *   `explosion`
*   **`frame_count`**: The total number of frames in the animation.
    *   `6`
*   **`frame_width`**: The width of each individual frame.
    *   `131`
*   **`frame_height`**: The height of each individual frame.
    *   `131`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `6`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.03`
*   **`loop`**: Whether the animation should loop. `0` indicates it does not loop.
    *   `0`
*   **`shrink_by_one_pixel`**: A visual effect parameter.
    *   `1`
*   **`pos_x`**: X-coordinate within the sprite sheet for the animation's starting position.
    *   `0`
*   **`pos_y`**: Y-coordinate within the sprite sheet for the animation's starting position.
    *   `1`