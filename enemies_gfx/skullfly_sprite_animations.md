---
title: Skullfly Sprite Animations
category: enemies_gfx
---

# Skullfly Sprite Animations

This document details the sprite animations for the Skullfly enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/skullfly.png` - The path to the sprite sheet.
*   **offset\_x**: `14` - Horizontal offset for sprite positioning.
*   **offset\_y**: `24` - Vertical offset for sprite positioning.
*   **default\_animation**: `"stand"` - The animation to play by default.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The starting X coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y coordinate of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (plays once), `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates frames are shrunk by one pixel, `0` (or omitted) means they are not.

### Defined Animations:

| Animation Name     | Frame Count | Frame Wait | Loop | Pos Y | Key Events