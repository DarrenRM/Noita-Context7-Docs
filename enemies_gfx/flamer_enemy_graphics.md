---
title: Flamer Enemy Graphics
category: enemies_gfx
---

# Flamer Enemy Graphics

This document details the graphical animations and associated events for the "Flamer" enemy in Noita.

## Sprite Definition

The main `<Sprite>` tag defines the base properties for the Flamer's visual representation.

### Key Attributes

| Attribute      | Value   | Description                                     |
| -------------- | ------- | ----------------------------------------------- |
| `filename`     | `data/enemies_gfx/flamer.png` | Path to the sprite sheet image.                 |
| `offset_x`     | `8`     | Horizontal offset for sprite positioning.       |
| `offset_y`     | `15`    | Vertical offset for sprite positioning.         |
| `default_animation` | `stand` | The animation to play by default.               |

## Animations

The Flamer has several distinct animations, each defined by a `<RectAnimation>` tag. These animations are crucial for defining the enemy's behavior and visual feedback.

### Animation Details

| Animation Name   | Frame Count | Frame Size (W x H) | Frame Wait | Frames Per Row | Loop | Description                                     |
| ---------------- | ----------- | ------------------ | ---------- | -------------- | ---- | ----------------------------------------------- |
| `stand`          | 6           | 17x19              | 0.2        | 8              | Yes  | Idle standing animation.                        |
| `walk`           | 4           | 17x19              | 0.1        | 8              | Yes  | Walking animation.                              |
| `run`            | 4           | 17x19              | 0.1        | 8              | Yes  | Running animation.                              |
| `jump_up`        | 1           | 17x19              | 0.082      | 8              | No   | Jumping upwards animation.                      |
| `jump_fall`      | 1           | 17x19              | 0.082      | 8              | Yes  | Falling animation after jump.                   |
| `land`           | 3           | 16x18              | 0.09       | 8              | No   | Landing animation.                              |
| `attack_ranged`  | 3           | 17x19              | 0.08       | 8              | No   | Ranged attack animation.                        |
| `fly_idle`       | 2           | 17x19              | 0.12       | 8              | Yes  | Idle flying animation.                          |
| `fly_move`       | 2           | 17x19              | 0.12       | 8              | Yes  | Moving while flying animation.                  |
| `burn`           | 4           | 17x19              | 0.06       | 8              | Yes  | Burning animation.                              |

### Animation Attributes

*   `frame_count`: The total number of frames in the animation.
*   `frame_height`, `frame_width`: Dimensions of each individual frame.
*   `frame_wait`: The time in seconds to display each frame.
*   `frames_per_row`: How many frames are arranged horizontally in the sprite sheet.
*   `name`: The identifier for the animation, used by the game engine.
*   `pos_x`, `pos_y`: The starting coordinates of the animation's frames within the sprite sheet.
*   `loop`: If set to `0`, the animation will not loop.
*   `shrink_by_one_pixel`: If set to `1`, the sprite will be shrunk by one pixel on each side, often used for smoother transitions or to avoid visual artifacts.

## Animation Events

Animations can trigger specific game events at certain frames. These events are defined using the `<Event>` tag within an animation.

### Key Event Attributes

| Attribute             | Description