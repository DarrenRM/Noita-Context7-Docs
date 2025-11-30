---
title: Question Mark Particle
category: particles
---

# Question Mark Particle

This documentation describes the configuration for the "Question Mark" particle effect in Noita, primarily used for visual feedback.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/particles/questionmark.png`
*   **`offset_x`**, **`offset_y`**: Adjust the sprite's position relative to its origin.
    *   `offset_x="3"`
    *   `offset_y="3"`
*   **`default_animation`**: Sets the animation to play by default when the particle is created.
    *   `default_animation="explosion"`

## Animation Details

The `RectAnimation` element defines the specific animation sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation, referenced by `default_animation`.
    *   `name="explosion"`
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet.
    *   `pos_x="0"`
    *   `pos_y="0"`
*   **`frame_count`**: The total number of frames in the animation.
    *   `frame_count="1"`
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
    *   `frame_width="6"`
    *   `frame_height="6"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `frame_wait="0.09"`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `frames_per_row="6"`
*   **`loop`**: Determines if the animation should repeat.
    *   `loop="1"` (meaning it loops)