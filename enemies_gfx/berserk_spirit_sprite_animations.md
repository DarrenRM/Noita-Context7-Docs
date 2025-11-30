---
title: Berserk Spirit Sprite Animations
category: data/enemies_gfx
---

# Berserk Spirit Sprite Animations

This document details the sprite animations for the Berserk Spirit enemy in Noita, as defined in its `berserkspirit.xml` file.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/berserkspirit.png` - The path to the sprite sheet.
*   **offset\_x**: `9` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `9` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The Berserk Spirit has several defined animations, primarily using the `<RectAnimation>` tag.

### Animation Details:

| Animation Name | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop |
| :------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- |
| `stand`        | 6           | 18          | 18           | 0.23       | 6              | 1    |
| `walk`         | 6           | 18          | 18           | 0.23       | 6              | 1    |
| `run`          | 6           | 18          | 18           | 0.23       | 6              | 1    |
| `burn`         | 6           | 18          | 18           | 0.23       | 6              | 1    |

### Notes:

*   All listed animations share the same sprite sheet coordinates (`pos_x="0"`, `pos_y="0"`).
*   The `run` and `burn` animations are explicitly noted as being copied from `walk`, indicating they use the same visual frames.
*   Each animation consists of 6 frames, each 18x18 pixels.
*   The frame wait time for all animations is 0.23 seconds.
*   All animations are set to loop (`loop="1"`).