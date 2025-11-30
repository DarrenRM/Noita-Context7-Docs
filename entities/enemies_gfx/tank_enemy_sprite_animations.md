---
title: Tank Enemy Sprite Animations
category: entities/enemies_gfx
---

---

# Tank Enemy Sprite Animations

This document details the sprite animations for the "tank" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/tank_emissive.png` - The path to the sprite sheet.
*   **offset\_x**: `9` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `17` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are present horizontally in the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; `1` (or omitted) indicates it loops.

### Animation Breakdown:

| Animation Name   | `pos_y` | `frame_count` | `frame_wait` | `loop` | Description                               |
| :--------------- | :------ | :------------ | :----------- | :----- | :---------------------------------------- |
| `stand`          | `0`     | `1`           | `0.16`       | `1`    | Idle animation.                           |
| `walk`           | `20`    | `4`           | `0.1`        | `1`    | Walking animation.                        |
| `run`            | `20`    | `4`           | `0.09`       | `1`    | Running animation.                        |
| `burn`           | `20`    | `4`           | `0.09`       | `1`    | Burning animation.                        |
| `attack`         | `40`    | `4`           | `0.07`       | `0`    | Melee attack animation.                   |
| `attack_ranged`  | `40`    | `4`           | `0.07`       | `0`    | Ranged attack animation.                  |
| `attack_grenade` | `60`    | `11`          | `0.04`       | `0`    | Grenade attack animation.                 |

**Note:** Animations `walk`, `run`, and `burn` share the same `pos_y` and `frame_width`/`frame_height`. The distinction between them is likely handled by game logic based on the animation name. The `frames_per_row` attribute is consistent across all animations, indicating a uniform layout of frames within the sprite sheet.