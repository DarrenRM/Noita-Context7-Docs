---
title: Gunpowder Smoke Particle
category: particles
---

---

# Gunpowder Smoke Particle

This document describes the configuration for a gunpowder smoke particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/smoke_gunpowder_01.png` - Specifies the texture file used for the particle.
*   **`offset_x`**: `10` - Horizontal offset for the sprite.
*   **`offset_y`**: `10` - Vertical offset for the sprite.
*   **`default_animation`**: `explosion` - The name of the animation to play by default.
*   **`rect_animation`**: `explosion` - Refers to the `RectAnimation` element that defines the sprite sheet animation.

## RectAnimation Configuration

The `RectAnimation` element details how to interpret the sprite sheet for animation.

### Key Attributes:

*   **`name`**: `explosion` - The identifier for this specific animation.
*   **`frame_count`**: `9` - The total number of frames in the animation.
*   **`frame_wait`**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **`frame_width`**: `20` - The width of a single frame in pixels.
*   **`frame_height`**: `20` - The height of a single frame in pixels.
*   **`frames_per_row`**: `12` - The number of frames that fit horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).

This particle is designed to be a visual effect, likely triggered by explosions or specific actions, and is not intended to have complex gameplay mechanics associated with it directly.