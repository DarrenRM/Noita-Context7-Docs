---
title: Ray Particle
category: particles
---

---

# Ray Particle

This documentation describes the configuration for the "ray" particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **filename**: Specifies the texture file for the sprite.
    *   `data/particles/ray.png`
*   **offset\_x**: Horizontal offset for the sprite's origin.
    *   `4.5`
*   **offset\_y**: Vertical offset for the sprite's origin.
    *   `4.5`
*   **default\_animation**: The name of the animation to play by default.
    *   `explosion`

## Animation Configuration

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: The identifier for this animation.
    *   `explosion`
*   **pos\_x**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **pos\_y**: Starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **frame\_count**: The total number of frames in the animation.
    *   `1`
*   **frame\_width**: The width of each individual frame.
    *   `9`
*   **frame\_height**: The height of each individual frame.
    *   `9`
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
    *   `0.03`
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
    *   `3`
*   **loop**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`