---
title: Handgun Sprite Data
category: items_gfx
---

# Handgun Sprite Data

This document details the sprite information for the Handgun item in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the handgun is defined within the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/handgun.png` - Specifies the path to the sprite image file.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated or displayed.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - The starting X position within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position within the sprite sheet.
*   **offset\_x**: `3` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `3` - Vertical offset for the sprite's origin.
*   **has\_offset**: `1` - Indicates that an offset is applied.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `6` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.