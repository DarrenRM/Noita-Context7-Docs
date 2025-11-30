---
title: Grass Patch 01 Sprite
category: data/vegetation/
---

# Grass Patch 01 Sprite

This document describes the sprite definition for `grass_patch_01.xml`, a common vegetation element in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and animation of the grass patch.

### Key Attributes

*   **filename**: `data/vegetation/grass_patch_01.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `10` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `9` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes

*   **name**: `vegetation_growth` - The name of this specific animation.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `20` - The width of each individual frame.
*   **frame\_height**: `10` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

### Special Note on `vegetation_growth`

The animation named `vegetation_growth` is a special designation in Noita. When used as the `default_animation` for a sprite, it triggers a unique visual effect where the vegetation appears to grow into existence.