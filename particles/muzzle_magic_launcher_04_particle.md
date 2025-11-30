---
title: Muzzle Magic Launcher 04 Particle
category: particles
---

# Muzzle Magic Launcher 04 Particle

This documentation describes the `muzzle_magic_launcher_04.xml` particle effect, used for muzzle flashes in Noita.

## Sprite

The primary visual component of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_04.png` - The image file for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `7` - Vertical offset for the sprite.
*   **default\_animation**: `muzzle` - The name of the animation to play by default.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).