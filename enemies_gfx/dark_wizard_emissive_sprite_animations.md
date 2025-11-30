---
title: Dark Wizard Emissive Sprite Animations
category: data/enemies_gfx/
---

# Dark Wizard Emissive Sprite Animations

This document details the sprite animations for the "dark wizard emissive" enemy in Noita, as defined in the `wizard_dark_emissive.xml` file. This file specifies the visual frames and timing for various actions the enemy performs.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its general properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_dark_emissive.png` - The path to the sprite sheet image.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `14` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Animation Table:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop | Notes                               |
| :--------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- | :---------------------------------- |
| `stand`          | 6           | 16          | 19           | 0.1        | 6              | 1    | Idle animation.                     |
| `walk`           | 6           | 16          | 19           | 0.085      | 6              | 1    | Walking animation.                  |
| `run`            | 6           | 16          | 19           | 0.085      | 6              | 1    | Running animation (copied from walk). |
| `burn`           | 6           | 16          | 19           | 0.085      | 6              | 1    | Burning animation (copied from walk). |
| `attack_ranged`  | 7           | 16          | 19           | 0.08       | 6              | 0    | Ranged attack animation.            |
| `fly_idle`       | 4           | 16          | 19           | 0.12       | 15             | 1    | Flying idle animation.              |
| `fly_move`       | 4           | 16          | 19           | 0.12       | 15             | 1    | Flying movement animation.          |

### Key Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., `stand`, `walk`).
*   **pos\_x**: The X-coordinate on the sprite sheet where the animation frames begin.
*   **pos\_y**: The Y-coordinate on the sprite sheet where the animation frames begin.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: The number of frames arranged horizontally on the sprite sheet for this animation.
*   **loop**: `1` for looping animations, `0` for non-looping animations.

**Note:** Some animations (`run`, `burn`) are explicitly noted as being copied from the `walk` animation, indicating they share the same visual frames and timing. The `attack_ranged` animation is non-looping, meaning it plays once and then typically transitions back to an idle or other appropriate state.