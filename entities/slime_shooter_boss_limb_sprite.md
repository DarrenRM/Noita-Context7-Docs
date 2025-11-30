---
title: Slime Shooter Boss Limb Sprite
category: entities
---

---

# Slime Shooter Boss Limb Sprite

This document details the sprite and animation data for the Slime Shooter Boss's limbs in Noita.

## Sprite Definition

The primary sprite for the boss limb is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_limbs/slimeshooter_boss.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` definitions, each describing a specific animation state.

### Animation States:

| Animation Name    | Description                                  | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop |
| :---------------- | :------------------------------------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- |
| **stand**         | Idle animation.                              | 4           | 16          | 24           | 0.23       | 6              | 1    |
| **walk**          | Walking animation.                           | 4           | 16          | 24           | 0.23       | 6              | 1    |
| **run**           | Running animation (copied from walk).        | 4           | 16          | 24           | 0.23       | 6              | 1    |
| **burn**          | Burning animation (copied from walk).        | 4           | 16          | 24           | 0.23       | 6              | 1    |
| **attack**        | Melee attack animation.                      | 4           | 16          | 24           | 0.07       | 6              | 0    |
| **attack\_ranged**| Ranged attack animation.                     | 4           | 16          | 24           | 0.07       | 6              | 0    |

### Animation Attributes:

*   **name**: The identifier for the animation state.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping animations.

**Note:** The `walk`, `run`, and `burn` animations share identical frame data. The `attack` and `attack_ranged` animations also share identical frame data and are positioned on a different row of the sprite sheet (`pos_y="24"`).