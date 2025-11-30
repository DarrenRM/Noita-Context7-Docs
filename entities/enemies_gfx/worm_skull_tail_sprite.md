---
title: Worm Skull Tail Sprite
category: entities/enemies_gfx
---

# Worm Skull Tail Sprite

This document describes the sprite data for the "worm_skull_tail" enemy in Noita.

## Sprite Attributes

The primary `Sprite` element defines the visual representation and animation for the worm skull tail.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_skull_tail.png` - The path to the sprite image file.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The sprite includes a single defined animation.

### `eat` Animation

*   **name**: `"eat"`
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `24` - The width of each individual frame.
*   **frame\_height**: `32` - The height of each individual frame.
*   **frame\_wait**: `0.082` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).