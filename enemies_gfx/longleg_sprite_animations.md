---
title: Longleg Sprite Animations
category: enemies_gfx
---

# Longleg Sprite Animations

This document details the sprite animations for the "Longleg" enemy in Noita, as defined in its `longleg.xml` file. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/longleg.png` - The texture file for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `6.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation.

### Common `<RectAnimation>` Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each frame in pixels.
*   **frame\_height**: The height of each frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: If present and set to `1`, each frame is shrunk by one pixel on all sides.

### Animation Breakdown:

| Animation Name | Frame Count | Frame Size (WxH) | Frame Wait | Loop | `pos_x` | `pos_y` | `shrink_by_one_pixel` | Key Events