---
title: Chainsaw Wand Sprite
category: items_gfx/wands/custom
---

# Chainsaw Wand Sprite

This documentation describes the sprite definition for the "chainsaw" wand in Noita.

## Sprite Definition

The primary sprite for the chainsaw wand is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/wands/custom/chainsaw.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.
*   **default\_animation**: `"default"` - Sets the default animation to be played.

## Animation Definition

The `default` animation is defined using the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `"default"` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for the animation frames.
*   **offset\_x**: `3.5` - Horizontal offset specific to this animation.
*   **offset\_y**: `3` - Vertical offset specific to this animation.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `2` - The total number of frames in this animation.
*   **frame\_width**: `14` - The width of each individual animation frame.
*   **frame\_height**: `6` - The height of each individual animation frame.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `10` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.