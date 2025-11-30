---
title: Lasershooter Emissive Sprite Data
category: entities
---

# Lasershooter Emissive Sprite Data

This document details the sprite data for the "lasershooter_emissive" enemy in Noita, focusing on its graphical animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the entity.

### Key Attributes:

*   **filename**: `data/enemies_gfx/lasershooter_emissive.png` - The path to the sprite sheet image.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `12` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` elements, each defining a specific animation sequence.

### Animation Details:

Each `<RectAnimation>` defines a set of frames from the sprite sheet.

#### Common Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: The horizontal starting position of the animation's frames within the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation's frames within the sprite sheet.

#### Specific Animations:

| Animation Name    | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Other Attributes        |
| :---------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :---------------------- |
| `stand`           | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                         |
| `walk`            | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                         |
| `run`             | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                         |
| `burn`            | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                         |
| `attack_ranged`   | 12          | 21          | 25           | 12             | 0.08       | 0     | 26    | `loop="0"`, `shrink_by_one_pixel="1"` |

**Summary of Animations:**

*   The `stand`, `walk`, `run`, and `burn` animations share similar frame dimensions and timings, suggesting they might use a common layout on the sprite sheet.
*   The `attack_ranged` animation is more detailed, with a higher frame count and a shorter frame wait time, indicating a more dynamic action. It also has `loop="0"` (meaning it plays once) and `shrink_by_one_pixel="1"`.