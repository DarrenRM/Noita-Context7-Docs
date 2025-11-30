---
title: Health Item Sprite
category: items_gfx
---

# Health Item Sprite

This document describes the sprite definition for the health item in Noita, focusing on its visual representation and animation.

## Sprite Definition

The `<Sprite>` element defines the base visual properties of the health item.

### Key Attributes:

*   **filename**: `data/items_gfx/health.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `6` - Vertical offset for the sprite's position.
*   **scale\_x**: `1` - Horizontal scaling factor.
*   **scale\_y**: `1` - Vertical scaling factor.

## Animation Definition

The `<RectAnimation>` element defines how the sprite animates.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `13` - The width of each individual frame.
*   **frame\_height**: `13` - The height of each individual frame.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.11` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **loop**: `1` - Indicates that the animation should loop continuously.
*   **shrink\_by\_one\_pixel**: `1` - A flag that might affect how the sprite is rendered or scaled.