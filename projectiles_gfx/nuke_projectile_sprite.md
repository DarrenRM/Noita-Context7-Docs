---
title: Nuke Projectile Sprite
category: projectiles_gfx
---

---

# Nuke Projectile Sprite

This documentation describes the sprite and animation data for the "nuke" projectile in Noita.

## Sprite

The main sprite definition for the nuke projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/nuke.png` - The path to the sprite image file.
*   **offset\_x**: `5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `default` - Specifies the name of the default animation to use.

## Animation: `default`

Defines the animation sequence for the nuke projectile.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `5` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes).