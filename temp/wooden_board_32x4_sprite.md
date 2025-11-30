---
title: Wooden Board 32x4 Sprite
category: data/temp/building
---

# Wooden Board 32x4 Sprite

This documentation describes the sprite definition for a wooden board asset in Noita.

## Sprite Definition

The primary element defines the visual representation of the wooden board.

### Key Attributes

*   **filename**: `data/temp/building/wooden_board32.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `0` - The vertical offset of the sprite's origin.

## Animation Definition

A `RectAnimation` element defines how the sprite is animated.

### Key Attributes

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `4` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).