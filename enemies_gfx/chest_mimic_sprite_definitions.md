---
title: Chest Mimic Sprite Definitions
category: data/enemies_gfx
---

# Chest Mimic Sprite Definitions

This document details the sprite definitions for the Chest Mimic enemy in Noita, focusing on its visual animations and associated properties.

## Sprite Properties

The main `<Sprite>` tag defines the base image and its positioning.

### Key Attributes:

*   **`filename`**: Specifies the path to the sprite sheet.
    *   `data/enemies_gfx/chest_mimic.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `12`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `16`
*   **`default_animation`**: The animation to play by default.
    *   `stand`

## Animations

The `<RectAnimation>` tags define individual animations for the Chest Mimic.

### Animation Details:

| Animation Name | `pos_x` | `pos_y` | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `frames_per_row` | `loop` | Notes                               |
| :------------- | :------ | :------ | :------------ | :------------ | :------------- | :----------- | :--------------- | :----- | :---------------------------------- |
| `stand`        | `0`     | `0`     | `1`           | `24`          | `20`           | `0.23`       | `7`              | `1`    | Base standing animation.            |
| `walk`         | `0`     | `0`     | `1`           | `24`          | `20`           | `0.23`       | `7`              | `1`    | Copied from `stand`.                |
| `run`          | `0`     | `0`     | `1`           | `24`          | `20`           | `0.23`       | `7`              | `1`    | Copied from `walk`.                 |
| `burn`         | `0`     | `20`    | `7`           | `24`          | `20`           | `0.09`       | `7`              | `1`    | Burning animation.                  |
| `attack`       | `0`     | `20`    | `7`           | `24`          | `20`           | `0.07`       | `7`              | `0`    | Attack animation (non-looping).     |

### Key Animation Attributes:

*   **`name`**: The identifier for the animation.
*   **`pos_x`, `pos_y`**: The starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`, `frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`loop`**: Whether the animation should repeat (`1` for loop, `0` for no loop).

## Animation Events

The `attack` animation includes an event that triggers specific game logic.

### `attack` Animation Event:

*   **`name`**: `attack_bite`
*   **`frame`**: `5` (The event triggers on the 5th frame of the animation).
*   **`probability`**: `1` (The event will always trigger when the frame is reached).
*   **`max_distance`**: `500` (Likely related to the range or effectiveness of the attack).
*   **`check_physics_material`**: `0` (Indicates this check is not performed for this event).
*   **`on_finished`**: `0` (Indicates the event does not depend on the animation finishing).