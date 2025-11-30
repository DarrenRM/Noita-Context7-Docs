---
title: Icer Sprite Animations
category: enemies_gfx
---

# Icer Sprite Animations

This document details the sprite animations for the "Icer" enemy in Noita, as defined in the `icer.xml` file. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/icer.png` - Path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `15` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played by default.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each individual frame in pixels.
*   **frame\_height**: Height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the top-left corner of the animation block on the sprite sheet.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation block on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it does.
*   **shrink\_by\_one\_pixel**: `1` indicates frames are shrunk by one pixel, useful for certain sprite designs.

### Animation Details:

| Animation Name   | Frame Count | Frame Size (W x H) | Frames Per Row | Frame Wait (s) | Pos (X, Y) | Loop | Key Events