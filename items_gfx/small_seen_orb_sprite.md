---
title: Small Seen Orb Sprite
category: items_gfx
---

```

# Small Seen Orb Sprite

This document describes the sprite data for the "Small Seen Orb" item in Noita, intended for AI-assisted modding.

## Sprite Definition

The core sprite definition for the orb.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_small_seen.png` - The path to the image file.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - Specifies the default animation to play.

## Animation: `default`

Defines the animation sequence for the orb.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).