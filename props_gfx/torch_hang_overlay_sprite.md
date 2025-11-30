---
title: Torch Hang Overlay Sprite
category: props_gfx
---

---

# Torch Hang Overlay Sprite

This document describes the sprite definition for the `torch_hang_overlay.xml` file, used for graphical elements in Noita.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_hang_overlay.png` - Specifies the path to the image file.
*   **offset\_x**: `5.5` - Horizontal offset for the sprite.
*   **offset\_y**: `13` - Vertical offset for the sprite.
*   **default\_animation**: `"default"` - The name of the animation to play by default.

## Animations

The sprite contains multiple `RectAnimation` elements, defining different animation states.

### Animation: `default`

This animation represents the standard state of the torch hang overlay.

*   **name**: `"default"`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `11` - Width of each frame.
*   **frame\_height**: `14` - Height of each frame.
*   **frame\_wait**: `0.1` - Time in seconds each frame is displayed.
*   **frames\_per\_row**: `1` - Number of frames per row in the sprite sheet.
*   **loop**: `1` - Whether the animation should loop (1 for true, 0 for false).

### Animation: `out`

This animation likely represents a state where the torch is "out" or extinguished.

*   **name**: `"out"`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `14` - Starting Y position within the sprite sheet. This indicates it's on a different row than the `default` animation.
*   **frame\_count**: `1`
*   **frame\_width**: `11`
*   **frame\_height**: `14`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `1`
*   **loop**: `1`