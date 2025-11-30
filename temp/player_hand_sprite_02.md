---
title: Player Hand Sprite 02
category: data
---

---

# Player Hand Sprite 02

This document describes the sprite data for the second player hand in Noita, used for visual representation.

## Sprite Attributes

The `<Sprite>` element defines the visual asset and its properties.

### Key Attributes:

*   **filename**: `data/temp/player_hand_02.png` - The path to the sprite image file.
*   **offset\_x**: `1` - Horizontal offset for the sprite.
*   **offset\_y**: `1.5` - Vertical offset for the sprite.
*   **default\_animation**: `hand` - The name of the default animation to play.

## Animations

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes for `hand` animation:

*   **name**: `hand` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `5` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).