---
title: Sheep Fly Sprite Animations
category: enemies_gfx
---

# Sheep Fly Sprite Animations

This document details the sprite animations for the "Sheep Fly" enemy in Noita, as defined in the `sheep_fly.xml` file. It focuses on the key attributes of each animation, providing a concise overview for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/sheep_fly.png` - The path to the sprite sheet.
*   **offset_x**: `10` - Horizontal offset for the sprite.
*   **offset_y**: `17` - Vertical offset for the sprite.
*   **default_animation**: `"walk"` - The animation that plays by default.

## RectAnimation Elements

Each `<RectAnimation>` defines a specific animation sequence.

### Common Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "fly_idle").
*   **pos_x**: The starting X coordinate of the animation frames on the sprite sheet.
*   **pos_y**: The starting Y coordinate of the animation frames on the sprite sheet.
*   **frame_count**: The total number of frames in the animation.
*   **frame_width**: The width of each individual frame.
*   **frame_height**: The height of each individual frame.
*   **frame_wait**: The duration (in seconds) each frame is displayed.
*   **frames_per_row**: The number of frames in a single row of the sprite sheet.
*   **loop**: `1` indicates the animation will loop, `0` means it will play once.
*   **has_offset**: `1` indicates that frame-specific offsets are applied.
*   **offset_x**: Frame-specific horizontal offset.
*   **offset_y**: Frame-specific vertical offset.

### Animation Details:

| Animation Name | `pos_y` | `frame_count` | `frame_wait` | Notes