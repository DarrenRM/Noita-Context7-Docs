---
title: Player Hand Sprite
category: data
---

---

# Player Hand Sprite

This document describes the sprite data for the player's hand in Noita, as defined in `player_hand_01.xml`. This sprite is used to visually represent the player's hand in the game.

## Sprite Definition

The primary sprite definition is contained within the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/temp/player_hand_01.png` - Specifies the image file used for the sprite.
*   **offset_x**: `1` - The horizontal offset of the sprite.
*   **offset_y**: `1.5` - The vertical offset of the sprite.
*   **default_animation**: `"hand"` - The name of the default animation to play for this sprite.

## Animation Definition

The sprite utilizes a single animation defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `"hand"` - The identifier for this animation.
*   **pos_x**: `"0"` - The starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `"0"` - The starting Y position of the animation frames within the sprite sheet.
*   **frame_count**: `"1"` - The total number of frames in this animation.
*   **frame_width**: `"5"` - The width of each individual animation frame.
*   **frame_height**: `"3"` - The height of each individual animation frame.
*   **frame_wait**: `"0.2"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `"1"` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `"0"` - Indicates whether the animation should loop (0 for no loop, 1 for loop).