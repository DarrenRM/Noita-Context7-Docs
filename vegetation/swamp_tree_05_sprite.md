---
title: Swamp Tree 05 Sprite
category: vegetation
---

# Swamp Tree 05 Sprite

This document describes the sprite and animation data for `swamp_tree_05.xml`, a vegetation asset in Noita.

## Sprite

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/swamp_tree_05.png` - The image file used for the sprite.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `175` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The animation that plays by default when this sprite is used.

## Animation: `vegetation_growth`

This sprite utilizes a special animation named `vegetation_growth`, which is designed to create a growing vegetation effect.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - The X position of the animation's starting frame within the sprite sheet.
*   **pos\_y**: `0` - The Y position of the animation's starting frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `64` - The width of each individual frame.
*   **frame\_height**: `180` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop (1 for true, 0 for false).