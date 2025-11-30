---
title: Wizard Neutral Sprite Animations
category: enemies_gfx
---

# Wizard Neutral Sprite Animations

This document details the sprite animations for the "wizard_neutral" entity in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `Sprite` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_neutral.png` - The primary image file for the sprite.
*   **hotspots_filename**: `data/enemies_gfx/wizard_hotspots.png` - Specifies the file containing collision and interaction points.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `14` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `Sprite` contains multiple `RectAnimation` elements, each defining a distinct animation.

### Common `RectAnimation` Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each individual frame.
*   **frame\_height**: Height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the animation's starting frame on the sprite sheet.
*   **pos\_y**: Y-coordinate of the animation's starting frame on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (default is `1` for looping).
*   **shrink\_by\_one\_pixel**: `1` indicates the sprite is shrunk by one pixel (often for animations that extend beyond the base sprite bounds).

### Notable Animations:

| Animation Name    | Frame Count | Frame Wait (s) | Frame Dimensions (WxH) | Pos X | Pos Y | Loop | Key Events