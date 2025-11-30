---
title: Pulserifle Sprite Data
category: items_gfx
---

# Pulserifle Sprite Data

This document details the sprite information for the "pulserifle" item in Noita, focusing on its visual representation and animation.

## Sprite Attributes

The `<Sprite>` tag defines the primary visual asset for the pulserifle.

### Key Attributes:

*   **filename**: `data/items_gfx/pulserifle.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `3` - Vertical offset of the sprite from its origin.
*   **scale\_x**: `1` - Horizontal scaling factor.
*   **scale\_y**: `1` - Vertical scaling factor.

## RectAnimation Data

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default` - The name of this animation sequence.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `19` - The width of each individual frame.
*   **frame\_height**: `8` - The height of each individual frame.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes).
*   **offset\_x**: `3` - Horizontal offset applied to the animation frames.
*   **offset\_y**: `4` - Vertical offset applied to the animation frames.