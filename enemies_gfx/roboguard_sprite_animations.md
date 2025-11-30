---
title: Roboguard Sprite Animations
category: enemies_gfx
---

# Roboguard Sprite Animations

This document details the sprite animations for the Roboguard enemy in Noita, as defined in `roboguard.xml`. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/roboguard.png` - The path to the sprite sheet.
*   **offset\_x**: `9` - Horizontal offset for the sprite.
*   **offset\_y**: `16` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation.

### Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each frame in pixels.
*   **frame\_height**: Height of each frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the animation's top-left corner on the sprite sheet.
*   **pos\_y**: Y-coordinate of the animation's top-left corner on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: If `1`, each frame is shrunk by one pixel.

### Notable Animations and Events:

| Animation Name   | Frame Count | Frame Wait | Loop | Key Events