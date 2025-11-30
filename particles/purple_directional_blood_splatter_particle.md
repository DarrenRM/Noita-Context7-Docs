---
title: Purple Directional Blood Splatter Particle
category: particles
---

---

# Purple Directional Blood Splatter Particle

This document describes the configuration for a specific particle effect in Noita, representing a directional purple blood splatter.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_purple_2.png`
    *   Specifies the image file used for the particle's texture.
*   **`offset_x`**: `8`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `8`
    *   Vertical offset for the sprite's origin.
*   **`default_animation`**: `smoke`
    *   The name of the default animation to be played when the particle is spawned.

## Animation Details

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **`name`**: `smoke`
    *   The identifier for this animation, referenced by `default_animation` in the `<Sprite>` tag.
*   **`pos_x`**: `0`
    *   Starting X position within the sprite sheet for the animation frames.
*   **`pos_y`**: `0`
    *   Starting Y position within the sprite sheet for the animation frames.
*   **`frame_count`**: `5`
    *   The total number of frames in this animation.
*   **`frame_width`**: `32`
    *   The width of each individual animation frame.
*   **`frame_height`**: `16`
    *   The height of each individual animation frame.
*   **`frame_wait`**: `0.025`
    *   The duration (in seconds) each frame is displayed before advancing to the next.
*   **`frames_per_row`**: `8`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).

This configuration suggests a particle that plays a short, non-looping animation of a purple blood splatter effect.