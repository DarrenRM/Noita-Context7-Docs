---
title: Skullrat Sprite Animations
category: data/enemies_gfx
---

# Skullrat Sprite Animations

This document details the sprite animations for the Skullrat enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/skullrat.png` - The path to the sprite sheet.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `13` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The starting X coordinate of the animation frames on the sprite sheet.
*   **pos\_y**: The starting Y coordinate of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates frames are shrunk by one pixel, often for smoother transitions.

### Animation Breakdown:

| Animation Name   | Frame Count | Frame Size (WxH) | Frames Per Row | Frame Wait (s) | Loop | Y Position | Key Events                               |
| :--------------- | :---------- | :--------------- | :------------- | :------------- | :--- | :--------- | :--------------------------------------- |
| `stand`          | 4           | 21x17            | 6              | 0.16           | Yes  | 1          | None                                     |
| `walk`           | 4           | 21x17            | 6              | 0.09           | Yes  | 18         | `step` (on frames 0 and 3)               |
| `run`            | 4           | 21x17            | 8              | 0.09           | Yes  | 18         | `step` (on frames 0 and 3)               |
| `burn`           | 4           | 21x17            | 8              | 0.09           | Yes  | 18         | `step` (on frames 0 and 3)               |
| `jump_up`        | 2           | 21x17            | 8              | 0.09           | No   | 35         | `jump` (on frame 0)                      |
| `jump_fall`      | 2           | 21x17            | 8              | 0.09           | No   | 52         | None                                     |
| `land`           | 2           | 21x17            | 8              | 0.09           | No   | 69         | `land` (on frame 0)                      |
| `attack`         | 6           | 21x17            | 8              | 0.05           | No   | 86         | `bite` (on frame 4)                      |
| `fly_idle`       | 8           | 21x17            | 8              | 0.04           | Yes  | 103        | None                                     |
| `fly_move`       | 8           | 21x17            | 8              | 0.04           | Yes  | 103        | None                                     |
| `jump_prepare`   | 3           | 21x17            | 8              | 0.08           | No   | 120        | `jump_start` (on frame 3)                |

## Event Definitions

Events are triggered at specific frames within an animation.

### Key Attributes for `Event`:

*   **name**: The name of the event (e.g., "step", "jump", "bite").
*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **probability**: The chance of the event triggering (usually `1` for guaranteed).
*   **on\_finished**: `0` means the event happens at the frame; `1` means it happens when the animation finishes.
*   **check\_physics\_material**: `1` means the event checks the physics material of the ground/surface.
*   **max\_distance**: Maximum distance for certain physics-related events.

### Notable Events:

*   **`step`**: Triggered during `walk`, `run`, and `burn` animations. Likely plays footstep sounds or effects.
*   **`jump`**: Triggered during `jump_up`.
*   **`land`**: Triggered during `land`.
*   **`bite`**: Triggered during `attack`.
*   **`jump_start`**: Triggered during `jump_prepare`.