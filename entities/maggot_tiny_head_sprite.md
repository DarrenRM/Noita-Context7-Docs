---
title: Maggot Tiny Head Sprite
category: entities
---

---

# Maggot Tiny Head Sprite

This document describes the sprite data for the "maggot_tiny_head" enemy in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The primary `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/maggot_tiny_head.png` - The path to the sprite image file.
*   **offset_x**: `72` - Horizontal offset for the sprite's origin.
*   **offset_y**: `48` - Vertical offset for the sprite's origin.
*   **default_animation**: `stand` - The animation to play by default.

## Animations

The sprite includes definitions for different animations, primarily using `<RectAnimation>`.

### `stand` Animation

*   **name**: `stand`
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_height**: `96` - Height of each animation frame.
*   **frame\_wait**: `0.082` - Time in seconds to wait between frames.
*   **frame\_width**: `96` - Width of each animation frame.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.

### `eat` Animation

*   **name**: `eat`
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_height**: `96` - Height of each animation frame.
*   **frame\_wait**: `0.082` - Time in seconds to wait between frames.
*   **frame\_width**: `96` - Width of each animation frame.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.

**Note:** Both `stand` and `eat` animations currently have identical frame data, suggesting they might be placeholders or share the same visual representation in this specific configuration.