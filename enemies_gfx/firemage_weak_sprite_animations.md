---
title: Firemage Weak Sprite Animations
category: enemies_gfx
---

# Firemage Weak Sprite Animations

This document details the sprite animations for the "firemage_weak" enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the core graphical assets and their properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/firemage_weak.png` - The primary image file for the sprite.
*   **hotspots\_filename**: `data/enemies_gfx/firemage_hotspots.png` - The image file defining collision and interaction points.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `20` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default.

### Hotspots:

*   **hand**: A defined point, likely for weapon/spell targeting or interaction.

## Animation Definitions

The `<RectAnimation>` tags define individual animations, specifying frame data and timing.

### Common Attributes for Animations:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame strip within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame strip within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.
*   **next\_animation**: Specifies the animation to transition to after completion (for non-looping animations).
*   **has\_offset**: `1` if the animation has specific X/Y offsets different from the main sprite.
*   **offset\_x**: Animation-specific horizontal offset.
*   **offset\_y**: Animation-specific vertical offset.

### Notable Animations and Events:

| Animation Name | `pos_y` | `frame_count` | `frame_wait` | `loop` | Key Events                                                              | Notes