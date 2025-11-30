---
title: Tiny Worm Body Sprite
category: entities
---

# Tiny Worm Body Sprite

This document describes the sprite definition for the "tiny worm body" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the enemy.

### Key Attributes

*   **filename**: `data/enemies_gfx/worm_tiny_body.png` - The path to the sprite image file.
*   **offset_x**: `9` - Horizontal offset for the sprite.
*   **offset_y**: `4.5` - Vertical offset for the sprite.
*   **default_animation**: `stand` - The animation to play by default.

## Animations

The `<RectAnimation>` tag defines specific animations for the sprite.

### `stand` Animation

*   **name**: `stand` - The name of this animation.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_height**: `9` - The height of each individual frame.
*   **frame_wait**: `0.082` - The time in seconds to wait between frames.
*   **frame_width**: `10` - The width of each individual frame.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **pos_x**: `0` - The X-coordinate of the top-left corner of the animation's frame within the sprite sheet.
*   **pos_y**: `0` - The Y-coordinate of the top-left corner of the animation's frame within the sprite sheet.