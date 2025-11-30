---
title: Noita Logo Animation Sprite
category: ui_gfx
---

# Noita Logo Animation Sprite

This document describes the sprite and animation data for the Noita logo displayed during loading screens.

## Sprite Data

The primary sprite definition for the Noita logo animation.

### Key Attributes:

*   **filename**: `data/ui_gfx/loading_splash/noita_logo_anim_01.png` - The texture file containing the logo frames.
*   **offset\_x**: `48` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `28` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"default"` - Specifies the name of the animation to play by default.

## Animation Data

Defines the parameters for the "default" animation of the Noita logo.

### Key Attributes:

*   **name**: `"default"` - The name of this animation.
*   **frame\_count**: `24` - The total number of frames in the animation.
*   **frame\_width**: `96` - The width of each individual frame in pixels.
*   **frame\_height**: `59` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `24` - The number of frames arranged horizontally in the texture file.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).