---
title: Jetpack Particle Sprite
category: particles
---

# Jetpack Particle Sprite

This document describes the sprite configuration for the jetpack particle effect in Noita.

## Sprite Configuration

The primary sprite element defines the visual appearance and animation of the jetpack particle.

### Key Attributes:

*   **filename**: `data/particles/jetpack.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `2.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"fireball"` - The name of the animation to play by default.

## Animation: `fireball`

This section details the `fireball` animation, which is used for the jetpack particle.

### Key Attributes:

*   **name**: `"fireball"` - The identifier for this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"6"` - The total number of frames in the animation.
*   **frame\_width**: `"7"` - The width of each individual frame in pixels.
*   **frame\_height**: `"7"` - The height of each individual frame in pixels.
*   **frame\_wait**: `"0.05"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"6"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"0"` - Indicates whether the animation should loop (0 for no loop, 1 for loop).