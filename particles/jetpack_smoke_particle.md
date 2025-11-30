---
title: Jetpack Smoke Particle
category: particles
---

---

# Jetpack Smoke Particle

This document describes the `jetpack_smoke.xml` particle definition, used to create the visual effect of smoke emitted from a jetpack in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/jetpack_smoke_Short.png` - Specifies the texture file for the particle's animation frames.
*   **offset_x**: `4` - Horizontal offset for the sprite.
*   **offset_y**: `4` - Vertical offset for the sprite.
*   **default_animation**: `explosion` - Sets the initial animation to play when the particle is spawned.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `explosion` - The name of this animation, referenced by `default_animation`.
*   **pos_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `8` - The width of each individual animation frame.
*   **frame_height**: `8` - The height of each individual animation frame.
*   **frame_wait**: `0.04` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation should not loop (play once).