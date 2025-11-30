---
title: Zombie Sprite Animations
category: data/enemies_gfx
---

# Zombie Sprite Animations

This document details the sprite animations for the Zombie enemy in Noita, as defined in `zombie.xml`. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/zombie.png` - The texture file for the zombie sprite.
*   **offset\_x**: `8.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation played when the zombie is idle.

## RectAnimation Elements

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation plays only once; omitted or `1` implies looping.
*   **shrink\_by\_one\_pixel**: `1` indicates the sprite is shrunk by one pixel, often used for specific animations like "run" or "burn".

### Notable Animations and Events:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait | Loop | Key Events