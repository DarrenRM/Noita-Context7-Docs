---
title: Grenade Launcher Sprite and Animation
category: items_gfx
---

# Grenade Launcher Sprite and Animation

This document describes the sprite and animation data for the Grenade Launcher item in Noita.

## Sprite

The primary sprite for the Grenade Launcher is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/grenadelauncher.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## RectAnimation

The `<RectAnimation>` tag defines the animation sequence for the Grenade Launcher.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for the animation.
*   **offset\_x**: `3` - Horizontal offset applied during animation.
*   **offset\_y**: `4` - Vertical offset applied during animation.
*   **has\_offset**: `1` - Indicates that offsets are used.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `17` - The width of each individual frame.
*   **frame\_height**: `6` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.