---
title: Swarm Firebug Projectile Sprite
category: projectiles_gfx
---

---

# Swarm Firebug Projectile Sprite

This document describes the sprite and animation data for the "swarm_firebug" projectile in Noita.

## Sprite Data

This section details the visual representation of the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/swarm_firebug.png` - The path to the sprite image file.
*   **offset\_x**: `4.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `4.5` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"fly"` - The name of the animation to play by default.

## Animation Data

This section defines the animations associated with the projectile sprite.

### Animation: `fly`

This animation controls the visual movement of the firebug projectile.

#### Key Attributes:

*   **name**: `"fly"` - The identifier for this animation.
*   **pos\_x**: `"0"` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"9"` - The width of each individual frame in pixels.
*   **frame\_height**: `"9"` - The height of each individual frame in pixels.
*   **frame\_wait**: `"0.07"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).