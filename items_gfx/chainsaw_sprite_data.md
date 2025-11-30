---
title: Chainsaw Sprite Data
category: items_gfx
---

---

# Chainsaw Sprite Data

This document details the sprite data for the Chainsaw item in Noita, focusing on its visual representation and animation.

## Sprite Definition

The primary sprite definition for the chainsaw is as follows:

*   **filename**: `data/items_gfx/chainsaw.png` - The path to the image file containing the chainsaw's graphics.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.
*   **default\_animation**: `default` - Specifies the name of the default animation to be used.

## Default Animation (`default`)

This section describes the animation sequence for the chainsaw.

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate for the animation's position.
*   **pos\_y**: `1` - Y-coordinate for the animation's position.
*   **offset\_x**: `3.5` - Horizontal offset specific to this animation.
*   **offset\_y**: `3` - Vertical offset specific to this animation.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `2` - The total number of frames in this animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `6` - The height of each individual frame.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally within the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop continuously.