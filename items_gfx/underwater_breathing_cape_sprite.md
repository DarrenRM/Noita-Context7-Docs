---
title: Underwater Breathing Cape Sprite
category: items_gfx
---

---

# Underwater Breathing Cape Sprite

This document describes the sprite data for the "Underwater Breathing" cape in Noita, used for its visual representation.

## Sprite Data

The primary sprite information is defined within the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/cape/breath_underwater.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's position.
*   **offset\_y**: `12` - Vertical offset for the sprite's position.
*   **default\_animation**: `default` - The name of the default animation to play.

## Animation Data

The sprite utilizes a single animation named "default".

### Key Attributes:

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).