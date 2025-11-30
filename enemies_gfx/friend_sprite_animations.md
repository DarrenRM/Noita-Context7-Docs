---
title: Friend Sprite Animations
category: enemies_gfx
---

# Friend Sprite Animations

This document details the sprite animations for the "Friend" entity in Noita, as defined in `data/enemies_gfx/friend.xml`. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/friend.png` - The path to the sprite sheet.
*   **offset\_x**: `15` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `24` - Vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation Definitions (`<RectAnimation>`)

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The X-coordinate on the sprite sheet where this animation's frames begin.
*   **pos\_y**: The Y-coordinate on the sprite sheet where this animation's frames begin.
*   **loop**: `0` indicates the animation plays once, while omitting it or setting to `1` implies looping.

### Notable Animations and their Events:

| Animation Name   | Frame Count | Frame Wait | Loop | Key Events