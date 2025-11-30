---
title: Scavenger Mine Sprite Animations
category: data/enemies_gfx
---

# Scavenger Mine Sprite Animations

This document details the sprite animations for the Scavenger Mine enemy in Noita, as defined in its XML configuration file. This information is crucial for understanding and modifying the visual behavior of this enemy.

## Sprite Configuration

The primary sprite configuration defines the base image and its offsets.

*   **filename**: `data/enemies_gfx/scavenger_mine.png` - The path to the sprite sheet.
*   **offset_x**: `8` - Horizontal offset of the sprite from its origin.
*   **offset_y**: `15` - Vertical offset of the sprite from its origin.
*   **default_animation**: `stand` - The animation to play by default.

## Key Animations

The following table summarizes the most important animations defined for the Scavenger Mine. Each animation is defined by a `RectAnimation` tag.

| Animation Name    | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Loop | Notes                                                              |
| :---------------- | :---------- | :---------- | :----------- | :------------- | :--- | :----------------------------------------------------------------- |
| `stand`           | 6           | 20          | 21           | 0.2            | 1    | Idle animation.                                                    |
| `walk`            | 6           | 20          | 21           | 0.082          | 1    | Movement animation. Triggers `step` events.                        |
| `run`             | 6           | 20          | 21           | 0.082          | 1    | Appears to be a copy of `walk`. Triggers `step` events.            |
| `burn`            | 6           | 20          | 21           | 0.06           | 1    | Burning animation. Triggers `step` events.                         |
| `jump_up`         | 3           | 20          | 21           | 0.082          | 0    | Animation for jumping upwards. Triggers `jump` event.              |
| `jump_fall`       | 2           | 20          | 21           | 0.082          | 0    | Animation for falling after a jump.                                |
| `attack_ranged`   | 3           | 20          | 21           | 0.07           | 0    | Ranged attack animation. Triggers `throw` event.                   |
| `fly_idle`        | 4           | 20          | 21           | 0.12           | 1    | Idle animation while flying.                                       |
| `fly_move`        | 4           | 20          | 21           | 0.09           | 1    | Movement animation while flying.                                   |
| `attack`          | 3           | 20          | 21           | 0.09           | 0    | Melee attack animation. Triggers `hit` event.                      |
| `attack_bullet`   | 12          | 20          | 21           | 0.11           | 0    | Bullet attack animation. Triggers `shoot_bullet` event.            |

### Animation Details

Each `RectAnimation` tag defines specific properties for an animation sequence:

*   **name**: The identifier for the animation (e.g., `stand`, `walk`).
*   **pos_x**: The X-coordinate on the sprite sheet where the animation frames begin.
*   **pos_y**: The Y-coordinate on the sprite sheet where the animation frames begin.
*   **frame_count**: The total number of frames in the animation.
*   **frame_width**: The width of each individual frame.
*   **frame_height**: The height of each individual frame.
*   **frame_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: The number of frames that fit horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping animations.

### Animation Events

Some animations include `Event` tags, which trigger specific game actions at certain frames.

*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **name**: The name of the event (e.g., `step`, `jump`, `throw`, `hit`, `shoot_bullet`).
*   **probability**: The probability of the event occurring (usually `1` for guaranteed events).
*   **check_physics_material**: If `1`, the event might be influenced by the physics material of the ground.

**Example Event (from `walk` animation):**

```xml
<Event frame="2" name="step" probability="1" check_physics_material="1"/>
```

This event signifies a "step" sound or action occurring on frame 2 of the `walk` animation, and it checks the ground's physics material.

---
```