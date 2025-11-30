---
title: Necromancer Super Emissive Sprite Animations
category: enemies_gfx
---

# Necromancer Super Emissive Sprite Animations

This document details the sprite animations for the "Necromancer Super Emissive" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/necromancer_super_emissive.png` - The path to the sprite sheet.
*   **`default_animation`**: `stand` - The animation to play by default.
*   **`offset_x`**: `16` - Horizontal offset for the sprite.
*   **`offset_y`**: `42` - Vertical offset for the sprite.

## RectAnimation Elements

Each `<RectAnimation>` defines a specific animation sequence.

### Common Attributes:

*   **`name`**: The identifier for the animation (e.g., `walk`, `attack`, `stand`).
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
*   **`pos_x`**: The starting X-coordinate of the animation frames on the sprite sheet.
*   **`pos_y`**: The starting Y-coordinate of the animation frames on the sprite sheet.
*   **`loop`**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.
*   **`shrink_by_one_pixel`**: If set to `1`, the sprite is shrunk by one pixel.

### Notable Animations and Events:

| Animation Name       | Frame Count | Frame Wait | Pos Y | Loop | Events