---
title: Purple Blood Splatter 3 Particle
category: particles
---

# Purple Blood Splatter 3 Particle

This document describes the configuration for a specific particle effect in Noita, representing a purple blood splatter.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_purple_3.png`
    *   Specifies the image file used for the particle's texture.
*   **`offset_x`**: `8`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `8`
    *   Vertical offset for the sprite's origin.
*   **`default_animation`**: `smoke`
    *   Sets the default animation to be played when the particle is spawned.

## Animation Definition

The particle utilizes a rectangular animation sequence.

### Key Attributes for `RectAnimation` (named "smoke"):

*   **`name`**: `smoke`
    *   The identifier for this animation.
*   **`pos_x`**: `0`
    *   Starting X position within the sprite sheet for the animation frames.
*   **`pos_y`**: `0`
    *   Starting Y position within the sprite sheet for the animation frames.
*   **`frame_count`**: `4`
    *   The total number of frames in this animation sequence.
*   **`frame_width`**: `16`
    *   The width of each individual animation frame.
*   **`frame_height`**: `16`
    *   The height of each individual animation frame.
*   **`frame_wait`**: `0.025`
    *   The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `8`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0`
    *   Indicates that the animation does not loop (plays only once).