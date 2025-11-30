---
title: Dummy Particle Sprite
category: particles
---

---

# Dummy Particle Sprite

This document describes the configuration for a basic dummy particle sprite used in Noita. It primarily defines the visual appearance and animation of the particle.

## Sprite Configuration

The `<Sprite>` element defines the core visual properties of the particle.

### Key Attributes:

*   **`filename`**: The path to the sprite image file.
    *   Example: `data/particles/dummy.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Example: `1.5`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Example: `1.5`
*   **`default_animation`**: The name of the animation to play by default.
    *   Example: `explosion`

## Animation Definition

The `<RectAnimation>` element specifies the details of a rectangular sprite sheet animation.

### Key Attributes:

*   **`name`**: The identifier for this animation, referenced by `default_animation` in the `<Sprite>` tag.
    *   Example: `explosion`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   Example: `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   Example: `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   Example: `1`
*   **`frame_width`**: The width of each individual frame.
    *   Example: `3`
*   **`frame_height`**: The height of each individual frame.
    *   Example: `3`
*   **`frame_wait`**: The time in seconds to wait between frames.
    *   Example: `0.02`
*   **`frames_per_row`**: The number of frames in a single row of the sprite sheet.
    *   Example: `1`
*   **`loop`**: Whether the animation should loop (1 for true, 0 for false).
    *   Example: `1`