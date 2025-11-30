---
title: Nuke Giga Projectile Graphics
category: projectiles_gfx
---

---

# Nuke Giga Projectile Graphics

This document details the graphical assets for the "Nuke Giga" projectile in Noita, as defined in `nuke_giga.xml`.

## Sprite Definition

The primary sprite for the projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/nuke.png` - Specifies the texture file used for the projectile's visual representation.
*   **offset\_x**: `5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `3.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"default"` - Indicates the name of the default animation to be used.

## Animation Details

The projectile utilizes a simple rectangular animation.

### Animation: `default`

*   **name**: `"default"` - The identifier for this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"12"` - The width of each individual animation frame.
*   **frame\_height**: `"7"` - The height of each individual animation frame.
*   **frame\_wait**: `"0.2"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"1"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"0"` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.