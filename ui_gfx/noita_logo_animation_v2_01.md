---
title: Noita Logo Animation v2 01
category: ui_gfx
---

# Noita Logo Animation v2 01

This document describes the configuration for the second version of the Noita logo animation used on loading screens.

## Sprite Configuration

The main `<Sprite>` element defines the visual asset and its initial positioning.

### Key Attributes:

*   **filename**: `data/ui_gfx/loading_splash/noita_logo_v2_anim_01.png` - The path to the sprite sheet containing the animation frames.
*   **offset\_x**: `55` - The horizontal offset of the sprite from its origin.
*   **offset\_y**: `30` - The vertical offset of the sprite from its origin.
*   **default\_animation**: `"default"` - Specifies the name of the animation to be played by default.

## RectAnimation Configuration

The `<RectAnimation>` element defines the properties of the animation itself.

### Key Attributes:

*   **name**: `"default"` - The identifier for this specific animation.
*   **frame\_count**: `24` - The total number of frames in the animation.
*   **frame\_width**: `110` - The width of each individual frame in pixels.
*   **frame\_height**: `61` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `24` - The number of frames arranged horizontally in the sprite sheet. This indicates that all frames are on a single row.
*   **loop**: `1` - Indicates that the animation should loop indefinitely (1 for true, 0 for false).