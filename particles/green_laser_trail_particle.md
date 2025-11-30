---
title: Green Laser Trail Particle
category: particles
---

---

# Green Laser Trail Particle

This document describes the configuration for the "laser_trail_green" particle effect in Noita, used to create a visual trail for green lasers.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/laser_trail_green.png` - Specifies the texture file used for the particle's sprite.
*   **offset\_x**: `4` - Horizontal offset for the sprite.
*   **offset\_y**: `0.5` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The name of the animation to play by default.

## Animation: "stand"

The `RectAnimation` element defines the specific animation sequence for the particle.

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `"0"` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `"6"` - The total number of frames in this animation.
*   **frame\_width**: `"8"` - The width of each individual animation frame.
*   **frame\_height**: `"1"` - The height of each individual animation frame.
*   **frame\_wait**: `"0.05"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"6"` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `"0"` - Indicates whether the animation should loop (0 for no loop, 1 for loop).