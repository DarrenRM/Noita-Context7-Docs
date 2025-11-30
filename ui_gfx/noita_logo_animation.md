---
title: Noita Logo Animation
category: ui_gfx
---

# Noita Logo Animation

This document describes the XML configuration for the Noita logo animation used on loading screens.

## Sprite

The main `Sprite` element defines the visual asset and its basic properties.

### Key Attributes:

*   **filename**: The path to the sprite sheet containing the animation frames.
    *   `data/ui_gfx/loading_splash/noita_logo_v3_anim_01.png`
*   **offset\_x**: Horizontal offset for the sprite.
    *   `55`
*   **offset\_y**: Vertical offset for the sprite.
    *   `34`
*   **default\_animation**: The name of the animation to play by default.
    *   `default`

## RectAnimation

The `RectAnimation` element defines the specific animation sequence.

### Key Attributes:

*   **name**: The name of this animation.
    *   `default`
*   **frame\_count**: The total number of frames in the animation.
    *   `32`
*   **frame\_width**: The width of each individual frame.
    *   `110`
*   **frame\_height**: The height of each individual frame.
    *   `69`
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.03`
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
    *   `32`
*   **loop**: Determines if the animation should repeat.
    *   `1` (meaning loop indefinitely)