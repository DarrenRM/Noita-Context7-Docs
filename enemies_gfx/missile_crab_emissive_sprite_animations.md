---
title: Missile Crab Emissive Sprite Animations
category: data/enemies_gfx
---

# Missile Crab Emissive Sprite Animations

This document details the sprite animations for the Missile Crab enemy, focusing on its emissive graphical elements.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its general properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/missilecrab_emissive.png` - The path to the sprite sheet containing all animation frames.
*   **offset_x**: `10` - Horizontal offset for the sprite's origin.
*   **offset_y**: `16` - Vertical offset for the sprite's origin.
*   **default_animation**: `"stand"` - The animation that plays by default when the entity is idle.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence for the Missile Crab.

### Animation Breakdown:

| Animation Name    | Description        | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Frames Per Row | Loop | Notes                               |
| :---------------- | :----------------- | :---------- | :---------- | :----------- | :------------- | :------------- | :--- | :---------------------------------- |
| `stand`           | Idle/Standing      | 4           | 24          | 20           | 0.1            | 6              | 1    |                                     |
| `walk`            | Walking            | 6           | 24          | 20           | 0.08           | 6              | 1    |                                     |
| `run`             | Running            | 6           | 24          | 20           | 0.08           | 6              | 1    | Copied from `walk`                  |
| `burn`            | Burning            | 6           | 24          | 20           | 0.08           | 6              | 1    | Copied from `walk`                  |
| `jump_up`         | Jumping upwards    | 4           | 24          | 20           | 0.09           | 8              | 0    |                                     |
| `land`            | Landing            | 2           | 24          | 20           | 0.082          | 8              | 0    |                                     |
| `attack_ranged`   | Ranged attack      | 8           | 24          | 20           | 0.12           | 8              | 0    |                                     |
| `alert`           | Taking damage      | 3           | 24          | 20           | 0.09           | 8              | 0    |                                     |
| `jump_prepare`    | Preparing to jump  | 3           | 24          | 20           | 0.06           | 8              | 0    | Event `jump_start` on frame 3       |
| `aim`             | Aiming             | 4           | 24          | 20           | 0.04           | 8              | 1    |                                     |

### Key Animation Attributes:

*   **name**: The identifier for the animation (e.g., `stand`, `walk`).
*   **pos_x**, **pos_y**: The starting coordinates of the animation frames within the sprite sheet. These values indicate which row of frames is used for each animation.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: The number of frames that fit horizontally on a single row of the sprite sheet.
*   **loop**: `1` for looping animations, `0` for one-time animations.
*   **Event**: Some animations can trigger specific game events at certain frames (e.g., `jump_start` on frame 3 of `jump_prepare`).