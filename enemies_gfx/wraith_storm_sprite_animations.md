---
title: Wraith Storm Sprite Animations
category: data/enemies_gfx
---

# Wraith Storm Sprite Animations

This document details the sprite animations for the Wraith Storm enemy in Noita, as defined in its `wraith_storm.xml` file. This file specifies the visual appearance and animation frames for the enemy.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes

*   **filename**: `data/enemies_gfx/wraith_storm.png` - The path to the sprite sheet containing all animation frames.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animation Definitions

The `<RectAnimation>` tags define individual animations. For the Wraith Storm, most animations appear to be identical, suggesting a simple visual representation or that specific animations are handled by other game logic.

### Animation Details

| Animation Name | `pos_x` | `pos_y` | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `frames_per_row` | `loop` |
| :------------- | :------ | :------ | :------------ | :------------ | :------------- | :----------- | :--------------- | :----- |
| `stand`        | 0       | 0       | 1             | 24            | 24             | 0.23         | 6                | 1      |
| `walk`         | 0       | 0       | 1             | 24            | 24             | 0.23         | 6                | 1      |
| `run`          | 0       | 0       | 1             | 24            | 24             | 0.23         | 6                | 1      |
| `burn`         | 0       | 0       | 1             | 24            | 24             | 0.23         | 6                | 1      |
| `fly_idle`     | 0       | 0       | 1             | 24            | 24             | 0.23         | 6                | 1      |
| `fly_move`     | 0       | 0       | 1             | 24            | 24             | 0.23         | 6                | 1      |

### Common Attributes Across Animations

*   **`pos_x` and `pos_y`**: All animations start at the top-left corner (0,0) of the sprite sheet.
*   **`frame_count`**: Set to `1`, indicating that each animation uses only a single frame from the sprite sheet.
*   **`frame_width` and `frame_height`**: Each frame is 24x24 pixels.
*   **`frame_wait`**: The delay between frames is 0.23 seconds.
*   **`frames_per_row`**: This value (6) is relevant for sprite sheets with multiple frames arranged horizontally, though with `frame_count` of 1, it doesn't directly impact the animation playback in this specific case.
*   **`loop`**: Set to `1`, meaning the animation will loop indefinitely.

**Note:** The identical configuration for `stand`, `walk`, `run`, `burn`, `fly_idle`, and `fly_move` suggests that the visual representation for the Wraith Storm is very basic, or that its movement and state changes are primarily driven by other game mechanics rather than distinct sprite frames.