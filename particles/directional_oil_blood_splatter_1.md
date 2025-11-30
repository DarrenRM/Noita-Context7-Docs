---
title: Directional Oil Blood Splatter 1
category: particles
---

# Directional Oil Blood Splatter 1

This documentation describes the `bloodsplatter_directional_oil_1.xml` file, which defines a specific type of blood splatter particle effect in Noita. This particle is characterized by its directional nature and an oily appearance.

## Sprite Definition

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/particles/bloodsplatters/bloodsplatter_directional_oil_1.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Definition

The particle utilizes a rectangular animation for its visual sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `smoke`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `5`
*   **`frame_width`**: The width of each individual frame.
    *   `32`
*   **`frame_height`**: The height of each individual frame.
    *   `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.025`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`