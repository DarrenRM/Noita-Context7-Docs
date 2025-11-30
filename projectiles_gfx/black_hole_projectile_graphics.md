---
title: Black Hole Projectile Graphics
category: projectiles_gfx
---

# Black Hole Projectile Graphics

This document describes the graphical assets for the "black hole" projectile in Noita, as defined in `black_hole.xml`.

## Sprite Definition

The primary sprite definition for the black hole projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/black_hole.png` - The texture file used for the sprite.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the default animation to play.

## Animations

### `fireball` Animation

This animation defines the visual sequence for the black hole projectile.

#### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `10` - The total number of frames in the animation.
*   **frame\_width**: `24` - The width of each individual frame.
*   **frame\_height**: `24` - The height of each individual frame.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.