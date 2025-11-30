---
title: Blue Directional Blood Splatter 3 Particle
category: particles
---

# Blue Directional Blood Splatter 3 Particle

This document describes the configuration for a specific particle effect in Noita, representing a blue directional blood splatter.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/bloodsplatters/bloodsplatter_directional_blue_3.png`
    *   Specifies the image file used for the particle's texture.
*   **offset_x**: `8`
    *   Horizontal offset for the sprite's origin.
*   **offset_y**: `8`
    *   Vertical offset for the sprite's origin.
*   **default_animation**: `smoke`
    *   The name of the default animation to be played when the particle is spawned.

## Animation Details

The particle utilizes a rectangular animation for its visual sequence.

### Animation: `smoke`

*   **name**: `smoke`
    *   Identifies this specific animation.
*   **pos_x**: `0`
    *   X-coordinate of the animation's starting position within the sprite sheet.
*   **pos_y**: `0`
    *   Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame_count**: `5`
    *   The total number of frames in this animation.
*   **frame_width**: `32`
    *   The width of each individual frame in pixels.
*   **frame_height**: `16`
    *   The height of each individual frame in pixels.
*   **frame_wait**: `0.025`
    *   The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `8`
    *   The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).