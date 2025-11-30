---
title: Enlightened Alchemist Sprite Animations
category: data/enemies_gfx
---

# Enlightened Alchemist Sprite Animations

This document details the sprite animations for the "Enlightened Alchemist" enemy in Noita, as defined in its XML configuration file. This information is crucial for modders looking to alter or create new animations for this entity.

## Sprite Definition

The primary sprite definition for the Enlightened Alchemist is as follows:

*   **Filename**: `data/enemies_gfx/enlightened_alchemist.png`
*   **Offset X**: `21` (Horizontal offset of the sprite's origin)
*   **Offset Y**: `34` (Vertical offset of the sprite's origin)
*   **Default Animation**: `stand` (The animation played when the entity is idle)

## Key Animations

The following table summarizes the key `RectAnimation` elements, highlighting their purpose and core properties.

| Animation Name | Frame Count | Frame Height | Frame Width | Frame Wait (sec) | Frames Per Row | Sprite Row Offset | Loop | Events |
| :------------- | :---------- | :----------- | :---------- | :--------------- | :------------- | :---------------- | :--- | :----- |
| `stand`        | 6           | 38           | 42          | 0.14             | 12             | 0                 | Yes  | None   |
| `walk`         | 6           | 38           | 42          | 0.12             | 12             | 38                | Yes  | None   |
| `run`          | 6           | 38           | 42          | 0.10             | 12             | 38                | Yes  | None   |
| `burn`         | 6           | 38           | 42          | 0.09             | 12             | 38                | Yes  | None   |
| `fly_idle`     | 6           | 38           | 42          | 0.11             | 12             | 0                 | Yes  | None   |
| `fly_move`     | 6           | 38           | 42          | 0.09             | 12             | 38                | Yes  | None   |
| `attack`       | 6           | 38           | 42          | 0.12             | 12             | 76                | No   | `attack_melee`, `voc_attack` |
| `attack_ranged`| 6           | 38           | 42          | 0.12             | 12             | 76                | No   | `attack_shoot` |

### Animation Details

Each `RectAnimation` tag defines a sequence of frames for a specific action.

*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_height` / `frame_width`**: The dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`name`**: The identifier for this animation, used by the game to trigger it.
*   **`pos_x` / `pos_y`**: The starting X and Y coordinates of the animation's frames within the sprite sheet. The `pos_y` value often indicates which row of the sprite sheet is used for this animation.
*   **`loop`**: If set to `0`, the animation will not repeat. By default, animations loop.

### Animation Events

Some animations can trigger specific game events at certain frames.

#### `attack` Animation Events

*   **Frame**: `4`
*   **Events**:
    *   `attack_melee`: Triggers a melee attack.
    *   `voc_attack`: Triggers a vocal attack.
*   **Properties**: `max_distance="500"`, `on_finished="0"`, `probability="1"`

#### `attack_ranged` Animation Events

*   **Frame**: `4`
*   **Event**:
    *   `attack_shoot`: Triggers a ranged projectile attack.
*   **Properties**: `max_distance="500"`, `on_finished="0"`, `probability="1"`

Modders can modify these values to alter the visual appearance, timing, and behavior of the Enlightened Alchemist's animations.