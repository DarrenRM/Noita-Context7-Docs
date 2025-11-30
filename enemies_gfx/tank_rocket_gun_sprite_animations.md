---
title: Tank Rocket Gun Sprite Animations
category: data/enemies_gfx
---

# Tank Rocket Gun Sprite Animations

This document details the sprite animations for the "tank_rocket_gun" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/tank_rocket_gun.png` - The path to the sprite sheet.
*   **`default_animation`**: `stand` - The animation played when no other animation is active.
*   **`offset_x`**: `9` - Horizontal offset for the sprite.
*   **`offset_y`**: `10` - Vertical offset for the sprite.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Animation Details:

| Animation Name    | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Loop | Shrink By One Pixel |
| :---------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :--- | :------------------ |
| `stand`           | 1           | 22          | 20           | 4              | 0.16       | 0     | 1     | N/A  | N/A                 |
| `walk`            | 4           | 22          | 20           | 4              | 0.1        | 0     | 22    | N/A  | N/A                 |
| `run`             | 4           | 22          | 20           | 4              | 0.09       | 0     | 22    | N/A  | N/A                 |
| `burn`            | 4           | 22          | 20           | 4              | 0.09       | 0     | 22    | N/A  | N/A                 |
| `attack`          | 5           | 23          | 21           | 5              | 0.07       | 0     | 43    | 0    | 1                   |
| `attack_ranged`   | 5           | 23          | 21           | 5              | 0.04       | 0     | 43    | 0    | 1                   |

### Key Attributes for `RectAnimation`:

*   **`name`**: The identifier for the animation (e.g., `stand`, `walk`, `attack`).
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
*   **`pos_x`**, **`pos_y`**: The starting coordinates of the animation's frames on the sprite sheet.
*   **`loop`**: `0` indicates the animation does not loop (typically for attack animations).
*   **`shrink_by_one_pixel`**: `1` indicates frames are slightly smaller, often used for attack animations to avoid clipping.

This data can be used to programmatically control or generate animations for the tank rocket gun enemy in custom mods.