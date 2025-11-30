---
title: Maggot Tiny Head Emissive Sprite
category: entities
---

# Maggot Tiny Head Emissive Sprite

This documentation describes the sprite definition for the "maggot_tiny_head_emissive" in Noita. It details the visual assets and animations used for this enemy's head.

## Sprite Definition

The main `<Sprite>` element defines the core visual properties and references the image file.

*   **filename**: `data/enemies_gfx/maggot_tiny_head_emissive.png` - The path to the sprite image file.
*   **offset\_x**: `72` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `48` - Vertical offset for the sprite's origin.
*   **default\_animation**: `stand` - The animation to play by default.

## Animations

The sprite includes definitions for different animations.

### `stand` Animation

This animation defines the "standing" state for the maggot's head.

*   **name**: `stand`
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_height**: `96` - Height of each frame in pixels.
*   **frame\_wait**: `0.082` - Delay between frames in seconds.
*   **frame\_width**: `96` - Width of each frame in pixels.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.

### `eat` Animation

This animation defines the "eating" state for the maggot's head.

*   **name**: `eat`
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_height**: `96` - Height of each frame in pixels.
*   **frame\_wait**: `0.082` - Delay between frames in seconds.
*   **frame\_width**: `96` - Width of each frame in pixels.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.