---
title: Directional Blood Splatter 3 Particle
category: particles
---

---

# Directional Blood Splatter 3 Particle

This document describes the configuration for a specific blood splatter particle effect in Noita, designed to appear directional.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/bloodsplatters/bloodsplatter_directional_3.png`
    *   Specifies the image file used for the particle's texture.
*   **offset_x**: `8`
    *   Horizontal offset for the sprite's origin.
*   **offset_y**: `8`
    *   Vertical offset for the sprite's origin.
*   **default_animation**: `smoke`
    *   Sets the default animation to be played when the particle is spawned.

## Animation Definition

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **name**: `smoke`
    *   The identifier for this animation, referenced by `default_animation` in the `<Sprite>` tag.
*   **pos_x**: `0`
    *   The starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0`
    *   The starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `5`
    *   The total number of frames in this animation.
*   **frame_width**: `32`
    *   The width of each individual animation frame.
*   **frame_height**: `16`
    *   The height of each individual animation frame.
*   **frame_wait**: `0.025`
    *   The duration (in seconds) each frame is displayed before advancing to the next.
*   **frames_per_row**: `8`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).