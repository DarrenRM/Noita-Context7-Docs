---
title: Root Grower Leaf Sprite
category: props_gfx
---

# Root Grower Leaf Sprite

This document describes the sprite definition for the "Root Grower Leaf" prop in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and animation of the prop.

### Key Attributes:

*   **filename**: `data/props_gfx/root_grower_leaf.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `17` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"grow"` - The name of the animation to play by default.

## Animations

The `<RectAnimation>` element defines a specific animation sequence.

### Grow Animation:

*   **name**: `"grow"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the texture.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the texture.
*   **frame\_count**: `5` - The total number of frames in this animation.
*   **frame\_width**: `30` - The width of each individual frame.
*   **frame\_height**: `30` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the texture.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).