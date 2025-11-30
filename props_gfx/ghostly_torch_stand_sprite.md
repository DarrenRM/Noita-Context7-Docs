---
title: Ghostly Torch Stand Sprite
category: props_gfx
---

---

# Ghostly Torch Stand Sprite

This documentation describes the sprite data for a ghostly torch stand, intended for use in AI-assisted Noita modding.

## Sprite Definition

The main `<Sprite>` element defines the visual asset and its properties.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_stand_emissive_ghostly.png` - The path to the sprite image file.
*   **offset_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset_y**: `18` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - Specifies the animation to play by default.

## Animations

The sprite utilizes `<RectAnimation>` elements to define different animation sequences.

### `default` Animation

This animation represents the standard, active state of the ghostly torch stand.

#### Key Attributes:

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously.

### `out` Animation

This animation likely represents a state where the torch stand is extinguished or fading.

#### Key Attributes:

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `19` - Starting Y position within the sprite sheet for this animation. This indicates it starts on the second row of frames.
*   **frame\_count**: `1` - The total number of frames in this animation (a single frame).
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.