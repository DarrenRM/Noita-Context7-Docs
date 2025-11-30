---
title: Ultimate Killer Sprite Animations
category: enemies_gfx
---

# Ultimate Killer Sprite Animations

This document details the sprite animations for the "Ultimate Killer" enemy in Noita, as defined in its `ultimate_killer.xml` file. It focuses on key animation attributes and events for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offsets.

### Key Attributes:

*   **filename**: `data/enemies_gfx/ultimate_killer.png` - The path to the sprite sheet.
*   **offset\_x**: `5` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<Sprite>` element contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The X-coordinate on the sprite sheet where this animation's frames begin.
*   **pos\_y**: The Y-coordinate on the sprite sheet where this animation's frames begin.
*   **loop**: `0` indicates the animation does not loop; `1` (or omitted) indicates it loops.

### Key Animations and Events:

| Animation Name   | Frame Count | Frame Wait | Loop | Key Events