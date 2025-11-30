---
title: Wolf Sprite Animations
category: enemies_gfx
---

# Wolf Sprite Animations

This document details the sprite animations for the Wolf enemy in Noita, focusing on key attributes for modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wolf.png` - The path to the sprite sheet.
*   **offset\_x**: `14` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `15` - Vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation played when the entity is idle.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates the sprite should be shrunk by one pixel, often used for smoother transitions or specific visual effects.

### Notable Animations and Events:

| Animation Name | Frame Count | Frame Wait | Loop | Key Events