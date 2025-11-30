---
title: Muzzle Launcher 02 Particle Effect
category: particles
---

# Muzzle Launcher 02 Particle Effect

This documentation describes the particle effect for the "Muzzle Launcher 02" in Noita, used to create muzzle flashes.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_launcher_02.png` - Specifies the texture file for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `7` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"muzzle"` - The name of the animation to play by default.

## Animation Definition

The animation for the muzzle flash is defined using the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `"muzzle"` - The identifier for this animation, referenced by the `<Sprite>` tag.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).