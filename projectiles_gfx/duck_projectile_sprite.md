---
title: Duck Projectile Sprite
category: projectiles_gfx
---

# Duck Projectile Sprite

This document describes the sprite and animation data for the "duck" projectile in Noita.

## Sprite Definition

The primary sprite for the duck projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/duck.png` - The path to the image file containing the sprite.
*   **offset\_x**: `7` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `6.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The name of the animation to play by default.

## Animations

The `<Sprite>` tag contains one or more `<RectAnimation>` tags, defining different animations.

### `stand` Animation

This animation defines the "standing" or idle state of the duck projectile.

#### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **frame\_count**: `2` - The total number of frames in this animation.
*   **frame\_height**: `13` - The height of each individual frame in pixels.
*   **frame\_width**: `14` - The width of each individual frame in pixels.
*   **frames\_per\_row**: `2` - The number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop indefinitely (1 for true, 0 for false).