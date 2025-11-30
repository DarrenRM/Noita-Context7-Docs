---
title: Wizard Tele Emissive Sprite Animations
category: entities
---

# Wizard Tele Emissive Sprite Animations

This document details the sprite animations for the "Wizard Tele Emissive" entity in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_tele_emissive.png` - The path to the sprite sheet.
*   **offset_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset_y**: `14` - Vertical offset for the sprite's origin.
*   **default_animation**: `stand` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for Animations:

*   **name**: The identifier for the animation (e.g., `stand`, `walk`, `attack_ranged`).
*   **pos_x**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame_count**: The total number of frames in the animation.
*   **frame_width**: The width of each individual frame.
*   **frame_height**: The height of each individual frame.
*   **frame_wait**: The duration (in seconds) each frame is displayed.
*   **frames_per_row**: How many frames are arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` for looping animations, `0` for non-looping.

### Animation Breakdown:

| Animation Name   | Start X | Start Y | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop | Notes                               |
| :--------------- | :------ | :------ | :---------- | :---------- | :----------- | :--------- | :------------- | :--- | :---------------------------------- |
| `stand`          | 0       | 0       | 6           | 16          | 19           | 0.1        | 6              | 1    | Default idle animation.             |
| `walk`           | 0       | 19      | 6           | 16          | 19           | 0.085      | 6              | 1    | Standard walking animation.         |
| `run`            | 0       | 19      | 6           | 16          | 19           | 0.085      | 6              | 1    | Copied from `walk`.                 |
| `burn`           | 0       | 19      | 6           | 16          | 19           | 0.085      | 6              | 1    | Copied from `walk`.                 |
| `attack_ranged`  | 0       | 38      | 7           | 16          | 19           | 0.08       | 6              | 0    | Ranged attack animation.            |
| `fly_idle`       | 0       | 57      | 4           | 16          | 19           | 0.12       | 15             | 1    | Idle animation while flying.        |
| `fly_move`       | 0       | 76      | 4           | 16          | 19           | 0.12       | 15             | 1    | Movement animation while flying.    |

**Note:** Animations `run` and `burn` are currently identical to `walk`. This might be an area for modding to add unique visual flair. The `frames_per_row` for `fly_idle` and `fly_move` is set to `15`, which is unusual given the `frame_width` and `frame_count`, suggesting these frames might be spread out differently on the sprite sheet or this value is not strictly adhered to for these specific animations.