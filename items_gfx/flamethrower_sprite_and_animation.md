---
title: Flamethrower Sprite and Animation
category: items_gfx
---

---

# Flamethrower Sprite and Animation

This documentation describes the sprite and animation data for the Flamethrower item in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the Flamethrower is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/flamethrower.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## Animation Definition

The Flamethrower utilizes a single animation named "default" defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **offset\_x**: `3` - Horizontal offset specific to this animation.
*   **offset\_y**: `4` - Vertical offset specific to this animation.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `15` - The width of each individual animation frame.
*   **frame\_height**: `9` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).