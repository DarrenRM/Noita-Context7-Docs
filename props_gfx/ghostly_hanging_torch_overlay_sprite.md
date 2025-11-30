---
title: Ghostly Hanging Torch Overlay Sprite
category: props_gfx
---

---

# Ghostly Hanging Torch Overlay Sprite

This document describes the sprite data for a ghostly hanging torch overlay used in Noita.

## Sprite Definition

The main sprite definition for the ghostly hanging torch overlay.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_hang_overlay_ghostly.png` - The path to the image file.
*   **offset\_x**: `5.5` - Horizontal offset of the sprite.
*   **offset\_y**: `13` - Vertical offset of the sprite.
*   **default\_animation**: `default` - The name of the default animation to play.

## Animations

This sprite uses `RectAnimation` to define its visual states.

### `default` Animation

This animation represents the standard state of the ghostly torch.

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `11` - Width of each frame.
*   **frame\_height**: `14` - Height of each frame.
*   **frame\_wait**: `0.1` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - Number of frames per row in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).

### `out` Animation

This animation likely represents a state where the torch is fading or extinguished.

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `14` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `11` - Width of each frame.
*   **frame\_height**: `14` - Height of each frame.
*   **frame\_wait**: `0.1` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - Number of frames per row in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop.