---
title: Basebot Soldier Sprite Animations
category: data/enemies_gfx
---

# Basebot Soldier Sprite Animations

This document details the sprite animations for the "Basebot Soldier" enemy in Noita, as defined in its XML configuration file. This information is crucial for understanding and potentially modifying the visual behavior of this enemy.

## Sprite Definition

The main `<Sprite>` tag defines the overall sprite properties and the default animation.

### Key Attributes:

*   **`default_animation`**: `stand` - The animation that plays by default when the enemy is idle.
*   **`filename`**: `data/enemies_gfx/basebot_soldier.png` - The path to the sprite sheet image file.
*   **`offset_x`**: `9` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `15` - Vertical offset for the sprite's origin.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `RectAnimation`:

*   **`name`**: The identifier for the animation (e.g., `stand`, `walk`, `attack`).
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame in pixels.
*   **`frame_height`**: The height of each individual frame in pixels.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: The starting X-coordinate of the animation frames on the sprite sheet.
*   **`pos_y`**: The starting Y-coordinate of the animation frames on the sprite sheet.
*   **`loop`**: `0` indicates the animation does not loop (e.g., for attacks). If omitted or `1`, it loops.
*   **`shrink_by_one_pixel`**: `1` indicates the sprite is shrunk by one pixel, often used for attack animations to give a sense of impact.

### Defined Animations:

| Animation Name | Frame Count | Frame Size (WxH) | Frame Wait (s) | Frames Per Row | Sprite Sheet Pos (X, Y) | Loop | Notes                               |
| :------------- | :---------- | :--------------- | :------------- | :------------- | :---------------------- | :--- | :---------------------------------- |
| `stand`        | 6           | 20x20            | 0.12           | 8              | (0, 1)                  | Yes  | Default idle animation.             |
| `fly_idle`     | 6           | 20x20            | 0.085          | 8              | (0, 1)                  | Yes  | Idle animation while flying.        |
| `walk`         | 4           | 20x20            | 0.09           | 8              | (0, 22)                 | Yes  | Walking animation.                  |
| `run`          | 4           | 20x20            | 0.09           | 8              | (0, 22)                 | Yes  | Running animation.                  |
| `burn`         | 4           | 20x20            | 0.09           | 8              | (0, 22)                 | Yes  | Animation when burning.             |
| `fly_move`     | 4           | 20x20            | 0.07           | 8              | (0, 22)                 | Yes  | Movement animation while flying.    |
| `attack`       | 5           | 21x21            | 0.05           | 8              | (0, 43)                 | No   | Melee or close-range attack.        |
| `attack_ranged`| 5           | 21x21            | 0.02           | 8              | (0, 43)                 | No   | Ranged attack animation.            |

## Animation Events

Events can be triggered at specific frames within an animation.

### Key Attributes for `Event`:

*   **`name`**: The type of event to trigger (e.g., `shoot_bullet`).
*   **`frame`**: The frame number (0-indexed) at which the event should occur.
*   **`probability`**: The chance (0-1) that the event will trigger.
*   **`on_finished`**: If `1`, the event triggers when the animation finishes.
*   **`max_distance`**: Maximum distance for certain events (e.g., projectile firing).
*   **`check_physics_material`**: If `1`, checks the physics material of the target.

### Defined Events:

*   **Animation `attack`**:
    *   **Event `shoot_bullet`**:
        *   `frame`: `3`
        *   `probability`: `1`
        *   `max_distance`: `500`
        *   `check_physics_material`: `0`
*   **Animation `attack_ranged`**:
    *   **Event `shoot_bullet`**:
        *   `frame`: `3`
        *   `probability`: `1`
        *   `max_distance`: `500`
        *   `check_physics_material`: `0`

These events indicate that at frame 3 of both `attack` and `attack_ranged` animations, a `shoot_bullet` event is triggered with a high probability and a maximum range.