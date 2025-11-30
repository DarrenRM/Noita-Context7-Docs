---
title: Failed Alchemist B Sprite Data
category: data/enemies_gfx
---

# Failed Alchemist B Sprite Data

This document details the sprite information for the "Failed Alchemist B" enemy in Noita, focusing on its graphical animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the enemy.

### Key Attributes:

*   **filename**: `data/enemies_gfx/failed_alchemist_b.png` - The path to the sprite sheet image.
*   **offset_x**: `8` - Horizontal offset of the sprite from its origin.
*   **offset_y**: `24` - Vertical offset of the sprite from its origin.
*   **default_animation**: `"stand"` - The animation that plays by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### Animation Details:

Each `<RectAnimation>` defines how a sequence of frames is extracted from the sprite sheet.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `name`           | The name of the animation (e.g., "stand", "walk", "burn").               |
| `frame_count`    | The total number of frames in this animation.                            |
| `frame_width`    | The width of each individual frame in pixels.                            |
| `frame_height`   | The height of each individual frame in pixels.                           |
| `frames_per_row` | How many frames are arranged horizontally on the sprite sheet.           |
| `frame_wait`     | The duration (in seconds) each frame is displayed before advancing.      |
| `pos_x`          | The X-coordinate on the sprite sheet where this animation starts.        |
| `pos_y`          | The Y-coordinate on the sprite sheet where this animation starts.        |

### Defined Animations:

| Animation Name | Frame Count | Frame Wait |
| :------------- | :---------- | :--------- |
| `stand`        | 6           | 0.07       |
| `walk`         | 6           | 0.08       |
| `run`          | 6           | 0.07       |
| `burn`         | 6           | 0.06       |
| `fly_idle`     | 6           | 0.07       |
| `fly_move`     | 6           | 0.06       |

**Note:** All animations share the same sprite sheet coordinates (`pos_x="0"`, `pos_y="0"`) and frame dimensions (`frame_width="16"`, `frame_height="27"`). The primary differences lie in the `frame_wait` attribute, which controls the animation speed.