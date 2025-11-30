---
title: Friend Fly Projectile Sprite
category: projectiles_gfx
---

# Friend Fly Projectile Sprite

This document describes the sprite definition for the "friend_fly" projectile in Noita. It details the visual appearance and animation of this projectile.

## Sprite Definition

The primary element is the `<Sprite>` tag, which defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/friend_fly.png` - The path to the sprite image file.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"fly"` - Specifies the default animation to be used.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"fly"` - The name of this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.035` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).