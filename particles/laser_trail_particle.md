---
title: Laser Trail Particle
category: particles
---

# Laser Trail Particle

This document describes the configuration for the `laser_trail.png` particle effect, commonly used for visual trails of lasers in Noita.

## Sprite Configuration

The primary sprite configuration defines the visual appearance and animation of the laser trail.

### Key Attributes:

*   **filename**: `data/particles/laser_trail.png` - Specifies the image file used for the particle.
*   **offset\_x**: `4` - Horizontal offset for the sprite.
*   **offset\_y**: `0.5` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The name of the animation to play by default.

## Animation: `stand`

This section details the `stand` animation, which controls how the `laser_trail.png` sprite is displayed over time.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `6` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `1` - The height of each individual animation frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).