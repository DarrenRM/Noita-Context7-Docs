---
title: Explosion Particle - Poof 128
category: particles
---

# Explosion Particle - Poof 128

This document describes the configuration for a specific explosion particle effect in Noita, named "explosion_128_poof". It utilizes a sprite sheet to animate a poofing explosion.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/explosion_128_poof.png`
    *   Specifies the image file used for the particle's visual representation.
*   **`offset_x`**: `64`
    *   The horizontal offset of the sprite's origin.
*   **`offset_y`**: `64`
    *   The vertical offset of the sprite's origin.
*   **`default_animation`**: `explosion`
    *   Indicates the name of the animation to be played by default when this sprite is used.

## Animation Configuration

The animation details for the "explosion" effect are defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **`name`**: `explosion`
    *   The identifier for this specific animation.
*   **`pos_x`**: `0`
    *   The starting X position within the sprite sheet for this animation.
*   **`pos_y`**: `0`
    *   The starting Y position within the sprite sheet for this animation.
*   **`frame_count`**: `5`
    *   The total number of frames in this animation.
*   **`frame_width`**: `128`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `128`
    *   The height of each individual frame in pixels.
*   **`frame_wait`**: `0.04`
    *   The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `5`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).