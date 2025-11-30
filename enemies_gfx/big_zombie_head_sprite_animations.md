---
title: Big Zombie Head Sprite Animations
category: enemies_gfx
---

# Big Zombie Head Sprite Animations

This document details the sprite animations for the "bigzombiehead" enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offset.

### Key Attributes:

*   **filename**: `data/enemies_gfx/bigzombiehead.png` - The path to the sprite sheet.
*   **offset\_x**: `12` - Horizontal offset of the sprite.
*   **offset\_y**: `20` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations.

### Common Attributes for Animations:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.

### Specific Animations:

| Animation Name   | `pos_y` | `frame_count` | `frame_wait` | `loop` | Key Events