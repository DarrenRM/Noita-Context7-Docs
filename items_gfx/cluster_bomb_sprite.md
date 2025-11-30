---
title: Cluster Bomb Sprite
category: items_gfx
---

---

# Cluster Bomb Sprite

This documentation describes the sprite definition for the "clusterbomb" item in Noita.

## Sprite Definition

The primary sprite for the cluster bomb is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/clusterbomb.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `4` - Horizontal offset for the sprite's position.
*   **offset\_y**: `4` - Vertical offset for the sprite's position.

## Animation Definition

The `<RectAnimation>` tag defines the animation for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **offset\_x**: `4` - Horizontal offset specific to this animation.
*   **offset\_y**: `4` - Vertical offset specific to this animation.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `8` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.