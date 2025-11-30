---
title: Basebot Soldier Emissive Sprite Animations
category: entities
---

# Basebot Soldier Emissive Sprite Animations

This document details the sprite animations for the `basebot_soldier_emissive.png` file, used for the Basebot Soldier enemy in Noita. It defines the visual appearance and animation sequences for various actions.

## Sprite Definition

The main `<Sprite>` tag defines the overall sprite properties and the default animation.

### Key Attributes:

*   **`default_animation`**: "stand" - The animation played when the entity is idle.
*   **`filename`**: "data/enemies_gfx/basebot_soldier_emissive.png" - The path to the sprite sheet.
*   **`offset_x`**: 9 - Horizontal offset for the sprite.
*   **`offset_y`**: 15 - Vertical offset for the sprite.

## Animation Sequences

The `<RectAnimation>` tags define individual animation states. Each animation is composed of frames from the sprite sheet.

### Animation Details:

| Animation Name | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait (s) | Position X | Position Y | Loop | Other Attributes |
| :------------- | :---------- | :---------- | :----------- | :------------- | :------------- | :--------- | :--------- | :--- | :--------------- |
| `stand`        | 6           | 20          | 20           | 8              | 0.12           | 0          | 1          | Yes  |                  |
| `fly_idle`     | 6           | 20          | 20           | 8              | 0.085          | 0          | 1          | Yes  |                  |
| `walk`         | 4           | 20          | 20           | 8              | 0.09           | 0          | 22         | Yes  |                  |
| `run`          | 4           | 20          | 20           | 8              | 0.09           | 0          | 22         | Yes  |                  |
| `burn`         | 4           | 20          | 20           | 8              | 0.09           | 0          | 22         | Yes  |                  |
| `fly_move`     | 4           | 20          | 20           | 8              | 0.07           | 0          | 22         | Yes  |                  |
| `attack`       | 5           | 21          | 21           | 8              | 0.05           | 0          | 43         | No   | `shrink_by_one_pixel="1"` |
| `attack_ranged`| 5           | 21          | 21           | 8              | 0.02           | 0          | 43         | No   | `shrink_by_one_pixel="1"` |

### Key Animation Attributes:

*   **`name`**: Identifies the animation state (e.g., "stand", "walk", "attack").
*   **`frame_count`**: The total number of frames in the animation sequence.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**, **`pos_y`**: The starting coordinates (top-left corner) of the animation frames within the sprite sheet.
*   **`loop`**: (Optional) If set to "0", the animation does not loop. Defaults to looping.
*   **`shrink_by_one_pixel`**: (Optional) A value of "1" indicates that each frame should be shrunk by one pixel, often used for attack animations to create a visual effect.