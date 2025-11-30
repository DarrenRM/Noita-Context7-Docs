---
title: Large Purple Blood Splatter 3 Particle
category: particles
---

# Large Purple Blood Splatter 3 Particle

This document describes the configuration for a specific particle effect in Noita, representing a large purple blood splatter.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_large_purple_3.png`
    *   Specifies the image file used for the sprite.
*   **`offset_x`**: `16`
    *   Horizontal offset of the sprite's origin.
*   **`offset_y`**: `16`
    *   Vertical offset of the sprite's origin.
*   **`default_animation`**: `smoke`
    *   The name of the default animation to play when the particle is spawned.

## Animation Details

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **`name`**: `smoke`
    *   The identifier for this specific animation.
*   **`frame_count`**: `6`
    *   The total number of frames in the animation.
*   **`frame_width`**: `33`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `33`
    *   The height of each individual frame in pixels.
*   **`frames_per_row`**: `8`
    *   The number of frames arranged horizontally within the sprite sheet.
*   **`frame_wait`**: `0.03`
    *   The duration (in seconds) each frame is displayed before advancing to the next.
*   **`loop`**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).
*   **`shrink_by_one_pixel`**: `1`
    *   A flag that likely causes the sprite to shrink by one pixel per frame, contributing to a fading or dissipating effect.
*   **`pos_x`**: `0`
    *   The starting X-coordinate within the sprite sheet for the animation frames.
*   **`pos_y`**: `1`
    *   The starting Y-coordinate within the sprite sheet for the animation frames.