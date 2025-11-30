---
title: Muzzle Launcher 04 Particle
category: particles
---

---

# Muzzle Launcher 04 Particle

This document describes the configuration for a muzzle flash particle effect, specifically `muzzle_launcher_04`.

## Sprite Configuration

The primary visual component of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_launcher_04.png` - Specifies the texture file used for the particle.
*   **offset_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset_y**: `7` - The vertical offset of the sprite's origin.
*   **default_animation**: `muzzle` - The name of the default animation to play.

## Animation Configuration

The animation details for the muzzle flash are defined within the `<RectAnimation>` element.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - The starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual animation frame.
*   **frame_height**: `16` - The height of each individual animation frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.