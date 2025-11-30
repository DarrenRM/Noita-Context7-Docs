---
title: Sheep Sprite Animations
category: entities_gfx
---

# Sheep Sprite Animations

This document details the sprite animations for the "Sheep" enemy in Noita, as defined in `sheep.xml`. It focuses on the key attributes of the `Sprite` and `RectAnimation` elements that define its visual behavior.

## Sprite Attributes

The main `Sprite` element defines the base image and default animation for the sheep.

*   **`filename`**: Specifies the path to the sprite sheet image.
    *   `data/enemies_gfx/sheep.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `10`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `12`
*   **`default_animation`**: The animation to play by default.
    *   `walk`

## RectAnimation Elements

Each `RectAnimation` defines a specific animation sequence for the sheep.

### Animation Definitions

| Name        | `pos_x` | `pos_y` | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `frames_per_row` | `loop` |
| :---------- | :------ | :------ | :------------ | :------------ | :------------- | :----------- | :--------------- | :----- |
| `stand`     | `0`     | `0`     | `4`           | `20`          | `20`           | `0.23`       | `6`              | `1`    |
| `walk`      | `0`     | `20`    | `6`           | `20`          | `20`           | `0.12`       | `6`              | `1`    |
| `run`       | `0`     | `20`    | `6`           | `20`          | `20`           | `0.12`       | `6`              | `1`    |
| `burn`      | `0`     | `20`    | `6`           | `20`          | `20`           | `0.12`       | `6`              | `1`    |
| `lower_head`| `0`     | `40`    | `4`           | `20`          | `20`           | `0.18`       | `6`              | `0`    |
| `eat`       | `0`     | `60`    | `2`           | `20`          | `20`           | `0.2`        | `6`              | `1`    |
| `raise_head`| `0`     | `80`    | `4`           | `20`          | `20`           | `0.18`       | `6`              | `0`    |
| `hurt`      | `0`     | `100`   | `3`           | `20`          | `20`           | `0.11`       | `6`              | `0`    |

### Key Animation Attributes

*   **`name`**: The identifier for the animation (e.g., `stand`, `walk`, `hurt`).
*   **`pos_x`**, **`pos_y`**: The starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`loop`**: `1` for looping animations, `0` for non-looping (one-shot) animations.

### Animation Events

Some animations include `Event` tags, which trigger specific game actions at certain frames.

*   **`walk` Animation Events**:
    *   Frame `2`: Triggers a `step` event with `probability="0.7"`.
    *   Frame `5`: Triggers a `step` event with `probability="0.7"`.
    *   `check_physics_material="1"`: Indicates that the game should check the physics material of the ground when this event occurs.

*   **`run` Animation Events**:
    *   Frame `2`: Triggers a `step` event with `probability="1"`.
    *   Frame `5`: Triggers a `step` event with `probability="1"`.

*   **`burn` Animation Events**:
    *   Frame `2`: Triggers a `step` event with `probability="1"`.
    *   Frame `5`: Triggers a `step` event with `probability="1"`.

*   **`eat` Animation Events**:
    *   Frame `1`: Triggers an `eat` event with `probability="0.7"`.
    *   `check_physics_material="0"`: Indicates that the game should *not* check the physics material for this event.