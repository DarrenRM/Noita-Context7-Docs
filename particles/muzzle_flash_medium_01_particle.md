---
title: Muzzle Flash Medium 01 Particle
category: particles
---

---

# Muzzle Flash Medium 01 Particle

This document describes the configuration for a medium-sized muzzle flash particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual component of the muzzle flash is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_medium_01.png` - Specifies the texture file used for the particle.
*   **offset_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset_y**: `7` - Vertical offset of the sprite's origin.
*   **default_animation**: `muzzle` - The name of the animation to be played by default.

## Animation Definition

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by `default_animation`.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.