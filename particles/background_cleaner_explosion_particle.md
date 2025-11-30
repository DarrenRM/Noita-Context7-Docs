---
title: Background Cleaner Explosion Particle
category: particles
---

# Background Cleaner Explosion Particle

This document describes the `background_cleaner_explosion.xml` file, which defines the visual appearance and animation of a particle effect used for explosions in Noita.

## Sprite

The primary visual component of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to use by default. In this case, it's "explosion".
*   **`filename`**: The path to the sprite sheet containing the animation frames.
*   **`offset_x`**, **`offset_y`**: Adjusts the positioning of the sprite.

## RectAnimation

Defines a rectangular animation sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation, matching `default_animation` in the `<Sprite>` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: Determines if the animation should loop (0 for no, 1 for yes).
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: A flag that affects how the sprite is rendered, potentially for visual effects.