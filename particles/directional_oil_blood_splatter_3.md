---
title: Directional Oil Blood Splatter 3
category: particles
---

---

# Directional Oil Blood Splatter 3

This documentation describes the `bloodsplatter_directional_oil_3.xml` file, which defines a specific blood splatter particle effect in Noita.

## Sprite Definition

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/particles/bloodsplatters/bloodsplatter_directional_oil_3.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Definition

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `smoke`
*   **`pos_x`**: The starting X position of the animation frames within the texture.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the texture.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `5`
*   **`frame_width`**: The width of each individual animation frame.
    *   `32`
*   **`frame_height`**: The height of each individual animation frame.
    *   `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.025`
*   **`frames_per_row`**: The number of frames arranged horizontally in the texture.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`

This particle effect appears to be a directional oil-based blood splatter with a short, non-looping animation.