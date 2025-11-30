---
title: Scavenger Poison Sprite Animations
category: enemies_gfx
---

# Scavenger Poison Sprite Animations

This document details the sprite animations for the "Scavenger Poison" enemy in Noita, as defined in its XML configuration file. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/scavenger_poison.png` - The path to the sprite sheet.
*   **offset\_x**: `13` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `21` - Vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for Animations:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.

### Notable Animations and Events:

| Animation Name   | Description        | Frame Count | Frame Wait | Loop | Key Events                                                              |
| :--------------- | :----------------- | :---------- | :--------- | :--- | :---------------------------------------------------------------------- |
| `stand`          | Idle animation     | 6           | 0.2        | 1    | None                                                                    |
| `walk`           | Walking animation  | 6           | 0.095      | 1    | `step` (frames 0, 3)                                                    |
| `run`            | Running animation  | 6           | 0.095      | 1    | `step` (frames 0, 3) - *Note: Copied from `walk`*                      |
| `burn`           | Burning animation  | 6           | 0.095      | 1    | `step` (frames 0, 3) - *Note: Copied from `walk`*                      |
| `jump_up`        | Jumping upwards    | 3           | 0.082      | 0    | `jump` (frame 0)                                                        |
| `jump_fall`      | Falling after jump | 3           | 0.082      | 0    | None                                                                    |
| `land`           | Landing animation  | 2           | 0.082      | 0    | `land` (frame 0)                                                        |
| `attack_ranged`  | Ranged attack      | 6           | 0.09       | 0    | `shoot_bullet` (frame 1)                                                |
| `fly_idle`       | Hovering animation | 4           | 0.12       | 1    | None                                                                    |
| `fly_move`       | Flying animation   | 4           | 0.09       | 1    | None                                                                    |
| `attack`         | Melee attack       | 4           | 0.09       | 0    | `hit` (frame 2)                                                         |
| `jump_prepare`   | Preparing to jump  | 3           | 0.1        | 0    | `jump_start` (frame 3)                                                  |

### Animation Events:

Events within animations trigger specific game actions.

*   **name**: The name of the event (e.g., `step`, `jump`, `land`, `shoot_bullet`, `hit`, `jump_start`).
*   **frame**: The frame number at which the event occurs.
*   **probability**: The chance of the event occurring (usually `1` for guaranteed events).
*   **check\_physics\_material**: If `1`, the event might be influenced by the physics material of the ground.

**Note on `run`, `burn`:** These animations appear to be direct copies of the `walk` animation in this file. For unique behavior, they would typically require distinct sprite frames and potentially different event timings.