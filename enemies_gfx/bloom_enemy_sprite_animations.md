---
title: Bloom Enemy Sprite Animations
category: entities_gfx
---

# Bloom Enemy Sprite Animations

This document details the sprite animations for the "Bloom" enemy in Noita, as defined in its `bloom.xml` file. It focuses on the key attributes of the `Sprite` and `RectAnimation` elements, along with important `Event` triggers.

## Sprite Element

The root element defining the sprite's properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/bloom.png` - The path to the sprite sheet image.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## RectAnimation Elements

These elements define individual animations for the enemy.

### Common Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates frames are slightly smaller than their defined dimensions.
*   **loop**: `0` for non-looping animations (e.g., "jump\_prepare", "attack\_ranged"), `1` (or omitted) for looping.

### Defined Animations:

| Animation Name    | Frame Count | Frame Wait | Pos Y | Loop | Key Events