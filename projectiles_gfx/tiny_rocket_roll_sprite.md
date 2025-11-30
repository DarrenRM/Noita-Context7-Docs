---
title: Tiny Rocket Roll Sprite
category: data/projectiles_gfx/
---

# Tiny Rocket Roll Sprite

This document describes the graphical assets for the "Tiny Rocket Roll" projectile in Noita, focusing on its sprite and animation.

## Sprite Definition

The core sprite definition for the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/rocket_tiny_roll.png` - The path to the image file containing the sprite.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `4.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to be used by default.

## Animation: `fireball`

Defines the animation sequence for the projectile.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `9` - The width of each individual frame in pixels.
*   **frame\_height**: `9` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).