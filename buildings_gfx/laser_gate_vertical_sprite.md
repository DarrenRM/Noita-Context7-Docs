---
title: Laser Gate Vertical Sprite
category: buildings_gfx
---

# Laser Gate Vertical Sprite

This document describes the sprite definition for the vertical laser gate in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and animation of the laser gate.

### Key Attributes:

*   **filename**: `data/buildings_gfx/lasergate_ver.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `4` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `0` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation that plays by default.

## Animation: `fireball`

The `<RectAnimation>` element defines a rectangular animation sequence.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `8` - The height of each individual animation frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).