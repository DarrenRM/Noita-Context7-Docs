---
title: Slime Spirit Graphics
category: entities
---

# Slime Spirit Graphics

This document details the graphical assets for the Slime Spirit enemy in Noita, focusing on its sprite and animations.

## Sprite Definition

The main sprite for the Slime Spirit is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/slimespirit.png` - Specifies the image file containing the sprite frames.
*   **`offset_x`**: `9` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `9` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `stand` - The animation that plays by default when the entity is idle.

## Animations

The Slime Spirit utilizes several `RectAnimation` definitions to control its visual states.

### Animation Details:

Each animation block defines how a sequence of frames from the sprite sheet is displayed.

| Animation Name | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `frames_per_row` | `loop` | Notes                               |
| :------------- | :------------ | :------------ | :------------- | :----------- | :--------------- | :----- | :---------------------------------- |
| `stand`        | 6             | 18            | 18             | 0.23         | 6                | 1      | Idle animation.                     |
| `walk`         | 6             | 18            | 18             | 0.23         | 6                | 1      | Walking animation.                  |
| `run`          | 6             | 18            | 18             | 0.23         | 6                | 1      | Running animation (copied from walk). |
| `burn`         | 6             | 18            | 18             | 0.23         | 6                | 1      | Burning animation (copied from walk). |

**Summary of Animation Attributes:**

*   **`name`**: The identifier for the animation (e.g., `stand`, `walk`).
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet. For the Slime Spirit, all animations start at `0,0`.
*   **`frame_count`**: The total number of frames in the animation sequence.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: `1` indicates the animation will repeat indefinitely.

**Note:** The `run` and `burn` animations are currently identical to the `walk` animation, suggesting they might be placeholders or intended to be visually similar.