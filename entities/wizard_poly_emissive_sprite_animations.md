---
title: Wizard Poly Emissive Sprite Animations
category: entities
---

# Wizard Poly Emissive Sprite Animations

This document details the sprite animations for the "wizard_poly_emissive" entity in Noita, focusing on its graphical representation and animation properties.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its positioning.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_poly_emissive.png` - The path to the sprite sheet.
*   **offset_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset_y**: `14` - Vertical offset for the sprite's origin.
*   **default_animation**: `"stand"` - The animation that plays by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations, specifying how frames are extracted from the sprite sheet and their timing.

### Animations:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop | Notes                               |
| :--------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- | :---------------------------------- |
| `stand`          | 6           | 16          | 19           | 0.1        | 6              | 1    | Standard standing animation.        |
| `walk`           | 6           | 16          | 19           | 0.085      | 6              | 1    | Walking animation.                  |
| `run`            | 6           | 16          | 19           | 0.085      | 6              | 1    | Copied from `walk`.                 |
| `burn`           | 6           | 16          | 19           | 0.085      | 6              | 1    | Copied from `walk`.                 |
| `attack_ranged`  | 7           | 16          | 19           | 0.08       | 6              | 0    | Ranged attack animation.            |
| `fly_idle`       | 4           | 16          | 19           | 0.12       | 15             | 1    | Idle animation while flying.        |
| `fly_move`       | 4           | 16          | 19           | 0.12       | 15             | 1    | Movement animation while flying.    |

### Key Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., `stand`, `walk`).
*   **pos_x**: The starting X coordinate on the sprite sheet for this animation's frames.
*   **pos_y**: The starting Y coordinate on the sprite sheet for this animation's frames.
*   **frame_count**: The total number of frames in the animation.
*   **frame_width**: The width of each individual frame.
*   **frame_height**: The height of each individual frame.
*   **frame_wait**: The duration (in seconds) each frame is displayed.
*   **frames_per_row**: How many frames are arranged horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.

---