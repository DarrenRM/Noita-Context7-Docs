---
title: Spell Refresh Sprite
category: items_gfx
---

# Spell Refresh Sprite

This documentation describes the sprite data for the "spell_refresh" item in Noita.

## Sprite Attributes

The primary sprite for the spell refresh item is defined by the following attributes:

*   **filename**: `data/items_gfx/spell_refresh.png` - The path to the sprite image file.
*   **offset_x**: `9` - Horizontal offset for the sprite.
*   **offset_y**: `20` - Vertical offset for the sprite.
*   **default_animation**: `default` - Specifies the default animation to use.

## RectAnimation: "default"

This section details the "default" animation for the spell refresh sprite.

*   **name**: `default` - The name of this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `20` - The width of each individual frame.
*   **frame_height**: `20` - The height of each individual frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).