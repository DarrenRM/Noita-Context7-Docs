---
title: Tank Super Gun Sprite Animations
category: enemies_gfx
---

# Tank Super Gun Sprite Animations

This document details the sprite animations for the "Tank Super Gun" enemy in Noita, as defined in its XML configuration file. It focuses on the key attributes of each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the overall sprite and its default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/tank_super_gun.png` - The path to the sprite image file.
*   **`default_animation`**: `stand` - The animation that plays by default when the enemy is idle.
*   **`offset_x`**: `9` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `10` - Vertical offset for the sprite's origin.

## Animation States

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation state.

### Animation States Table:

| Name            | `frame_count` | `frame_width` | `frame_height` | `frames_per_row` | `frame_wait` | `pos_x` | `pos_y` | `loop` | `shrink_by_one_pixel` | Notes                               |
| :-------------- | :------------ | :------------ | :------------- | :--------------- | :----------- | :------ | :------ | :----- | :-------------------- | :---------------------------------- |
| `stand`         | 1             | 22            | 20             | 11               | 0.16         | 0       | 1       | N/A    | N/A                   | Idle animation.                     |
| `walk`          | 4             | 22            | 20             | 11               | 0.1          | 0       | 22      | N/A    | N/A                   | Walking animation.                  |
| `run`           | 4             | 22            | 20             | 11               | 0.09         | 0       | 22      | N/A    | N/A                   | Running animation.                  |
| `burn`          | 4             | 22            | 20             | 11               | 0.09         | 0       | 22      | N/A    | N/A                   | Burning animation.                  |
| `attack`        | 4             | 22            | 20             | 11               | 0.07         | 0       | 43      | 0      | N/A                   | Standard attack animation.          |
| `attack_ranged` | 4             | 22            | 20             | 11               | 0.04         | 0       | 43      | N/A    | N/A                   | Ranged attack animation.            |
| `attack_grenade`| 4             | 23            | 21             | 11               | 0.04         | 0       | 64      | 0      | 1                     | Grenade attack animation.           |

### Key Attributes for `RectAnimation`:

*   **`name`**: The identifier for the animation state (e.g., `stand`, `walk`, `attack`).
*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **`loop`**: If set to `0`, the animation will not loop. Otherwise, it will loop.
*   **`shrink_by_one_pixel`**: If set to `1`, each frame will be shrunk by one pixel. This is often used for specific visual effects or to adjust sprite boundaries.