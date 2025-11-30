---
title: TNT Projectile Sprite
category: projectiles_gfx
---

---

# TNT Projectile Sprite

This document describes the sprite and animation data for the TNT projectile in Noita.

## Sprite

The main sprite for the TNT projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/tnt.png` - The path to the image file used for the sprite.
*   **offset\_x**: `3` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.

## RectAnimation

This section defines the animation for the TNT projectile.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - Starting X position within the sprite sheet.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet.
*   **offset\_x**: `3` - Horizontal offset for the animation frame.
*   **offset\_y**: `3` - Vertical offset for the animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `6` - The width of each animation frame.
*   **frame\_height**: `6` - The height of each animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.