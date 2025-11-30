---
title: Blue Hanging Torch Overlay Sprite
category: props_gfx
---

---

# Blue Hanging Torch Overlay Sprite

This document describes the sprite data for a blue hanging torch overlay in Noita.

## Sprite Definition

The primary sprite definition is handled by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_hang_overlay_blue.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `5.5` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `13` - Vertical offset of the sprite from its origin.
*   **default\_animation**: `default` - The name of the animation to play by default.

## Animations

The sprite utilizes two distinct animations: `default` and `out`.

### `default` Animation

This animation represents the standard state of the torch overlay.

#### Key Attributes:

*   **name**: `default`
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `11` - The width of each frame in pixels.
*   **frame\_height**: `14` - The height of each frame in pixels.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

### `out` Animation

This animation likely represents a state where the torch is extinguished or fading.

#### Key Attributes:

*   **name**: `out`
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `14` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet. This indicates the `out` animation starts below the `default` animation on the sprite sheet.
*   **frame\_count**: `1`
*   **frame\_width**: `11`
*   **frame\_height**: `14`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `1`
*   **loop**: `1`