---
title: Grass Patch 04 Sprite
category: data
---

# Grass Patch 04 Sprite

This document describes the sprite and animation data for `grass_patch_04.xml`, a vegetation asset in Noita.

## Sprite Information

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/grass_patch_04.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `10` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `9` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Data

The animation for this vegetation is defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each animation frame.
*   **frame\_height**: `10` - The height of each animation frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

### Special Note:

The `vegetation_growth` animation name is a special keyword in Noita. When used as `default_animation`, it signifies that this sprite is part of a growing vegetation system, implying a visual growth effect over time.