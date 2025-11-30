---
title: Drone Shield Sprite Definitions
category: data/enemies_gfx
---

# Drone Shield Sprite Definitions

This document details the sprite definitions for the "drone_shield" enemy in Noita, focusing on its visual animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and its positioning.

### Key Attributes:

*   **filename**: `data/enemies_gfx/drone_shield.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `7.5` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The name of the animation (e.g., "stand", "walk", "burn").
*   **frame\_count**: `10` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frames\_per\_row**: `10` - How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation frames on the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frames on the sprite sheet.

### Defined Animations:

| Animation Name | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait |
| :------------- | :---------- | :---------- | :----------- | :------------- | :--------- |
| `stand`        | 10          | 16          | 16           | 10             | 0.05       |
| `walk`         | 10          | 16          | 16           | 10             | 0.05       |
| `run`          | 10          | 16          | 16           | 10             | 0.05       |
| `burn`         | 10          | 16          | 16           | 10             | 0.05       |
| `fly_move`     | 10          | 16          | 16           | 10             | 0.05       |
| `fly_idle`     | 10          | 16          | 16           | 10             | 0.05       |

All defined animations share the same frame dimensions and timing, suggesting they are derived from a single 10x10 grid of 16x16 pixel frames within the `drone_shield.png` sprite sheet.