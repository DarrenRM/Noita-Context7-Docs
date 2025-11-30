---
title: Muzzle Flash Medium 03 Particle
category: particles
---

# Muzzle Flash Medium 03 Particle

This document describes the configuration for a muzzle flash particle effect in Noita, specifically `muzzle_medium_03.xml`.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_medium_03.png`
    *   Specifies the image file used for the particle's texture.
*   **offset_x**: `8`
    *   Horizontal offset of the sprite's origin.
*   **offset_y**: `7`
    *   Vertical offset of the sprite's origin.
*   **default_animation**: `muzzle`
    *   The name of the animation to be played by default.

## Animation Configuration

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `muzzle`
    *   The identifier for this animation, referenced by `default_animation` in the `<Sprite>` tag.
*   **pos_x**: `0`
    *   The starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0`
    *   The starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `1`
    *   The total number of frames in this animation.
*   **frame_width**: `16`
    *   The width of each individual animation frame.
*   **frame_height**: `16`
    *   The height of each individual animation frame.
*   **frame_wait**: `0.1`
    *   The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).

This configuration defines a simple, single-frame muzzle flash that appears briefly.