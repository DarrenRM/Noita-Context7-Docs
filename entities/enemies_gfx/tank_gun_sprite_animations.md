---
title: Tank Gun Sprite Animations
category: entities/enemies_gfx
---

# Tank Gun Sprite Animations

This document details the sprite animations for the "Tank Gun" enemy in Noita, as defined in `tank_gun.xml`. It focuses on the key attributes of the `Sprite` and `RectAnimation` elements, which are crucial for understanding and modifying the visual behavior of this enemy.

## Sprite Element

The root element defining the sprite's overall properties.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `"stand"`
*   **`filename`**: The path to the sprite sheet image.
    *   Value: `"data/enemies_gfx/tank_gun.png"`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   Value: `"9"`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   Value: `"10"`

## RectAnimation Elements

Each `RectAnimation` defines a specific animation sequence.

### Key Attributes:

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`pos_x`**: The horizontal starting position of the animation frames on the sprite sheet.
*   **`pos_y`**: The vertical starting position of the animation frames on the sprite sheet.
*   **`loop`**: (Optional) If set to `"0"`, the animation will not loop. Defaults to looping.
*   **`shrink_by_one_pixel`**: (Optional) If set to `"1"`, the sprite will be shrunk by one pixel.

### Defined Animations:

| Animation Name    | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Loop | Shrink |
| :---------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :--- | :----- |
| `stand`           | 1           | 22          | 20           | 11             | 0.16       | 0     | 1     | Yes  | No     |
| `walk`            | 4           | 22          | 20           | 11             | 0.1        | 0     | 22    | Yes  | No     |
| `run`             | 4           | 22          | 20           | 11             | 0.09       | 0     | 22    | Yes  | No     |
| `burn`            | 4           | 22          | 20           | 11             | 0.09       | 0     | 22    | Yes  | No     |
| `attack`          | 4           | 22          | 20           | 11             | 0.07       | 0     | 43    | No   | No     |
| `attack_ranged`   | 4           | 22          | 20           | 11             | 0.04       | 0     | 43    | Yes  | No     |
| `attack_grenade`  | 11          | 23          | 21           | 11             | 0.04       | 0     | 64    | No   | Yes    |

**Note:** Animations `walk`, `run`, `burn`, and `attack_ranged` share the same `pos_y` (22) and `pos_x` (0) on the sprite sheet, but differ in `frame_count` and `frame_wait`, indicating they use different segments of the same row or are visually distinct despite similar positioning. `attack` and `attack_ranged` also share a `pos_y` but have different `frame_wait` and `loop` behavior. `attack_grenade` uses a different row and has a slightly larger frame size and `shrink_by_one_pixel` enabled.