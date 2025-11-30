---
title: Worm Skull Body Sprite
category: entities
---

# Worm Skull Body Sprite

This document describes the sprite definition for the "worm_skull_body" entity in Noita.

## Sprite Definition

The primary sprite for the worm skull body is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/enemies_gfx/worm_skull_body.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `14` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `16` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is idle.

## Animations

The sprite definition includes animations that dictate how the sprite behaves.

### `eat` Animation

*   **name**: `"eat"` - The name of this specific animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `24` - The width of each individual frame.
*   **frame\_height**: `32` - The height of each individual frame.
*   **frame\_wait**: `0.082` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that this animation should loop (1 for true, 0 for false).