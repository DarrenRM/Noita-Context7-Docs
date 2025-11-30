---
title: Orange Tiny Smoke Particle
category: particles
---

---

# Orange Tiny Smoke Particle

This documentation describes the configuration for a small, orange smoke particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle sprite.
    *   `data/particles/smoke_orange_tiny.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Details

The `RectAnimation` element defines the specific animation sequence for the particle.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `smoke`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `3`
*   **`frame_width`**: The width of each individual animation frame.
    *   `16`
*   **`frame_height`**: The height of each individual animation frame.
    *   `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.04`
*   **`frames_per_row`**: The number of frames that fit horizontally in a single row of the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`

This particle is designed to be a small, short-lived visual effect, likely used for minor explosions or dissipating elements.