---
title: Bomb in Hand Sprite
category: items_gfx
---

# Bomb in Hand Sprite

This document describes the sprite data for the "bomb in hand" item in Noita, used for its visual representation when held by the player.

## Sprite Attributes

The main `<Sprite>` tag defines the visual asset and its positioning.

### Key Attributes:

*   **filename**: `data/items_gfx/in_hand/bomb_in_hand.png` - Specifies the image file for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `9` - Vertical offset for the sprite's position.
*   **default\_animation**: `default` - The name of the animation to play by default.

## Animations

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).