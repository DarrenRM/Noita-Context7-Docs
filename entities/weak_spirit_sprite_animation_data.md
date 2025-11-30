---
title: Weak Spirit Sprite Animation Data
category: entities
---

# Weak Spirit Sprite Animation Data

This document details the sprite animation data for the "Weak Spirit" enemy in Noita, focusing on its visual representation and animation states.

## Sprite Definition

The primary sprite for the Weak Spirit is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/weakspirit.png` - Specifies the image file containing the sprite frames.
*   **`offset_x`**: `9` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `9` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `stand` - The animation state that plays by default.

## Animation States

The Weak Spirit has several defined animation states, each controlled by a `<RectAnimation>` tag. These animations are derived from a single sprite sheet.

### Animation Details:

| Animation Name | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop |
| :------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- |
| `stand`        | 6           | 18          | 18           | 0.23       | 6              | 1    |
| `walk`         | 6           | 18          | 18           | 0.23       | 6              | 1    |
| `run`          | 6           | 18          | 18           | 0.23       | 6              | 1    |
| `burn`         | 6           | 18          | 18           | 0.23       | 6              | 1    |

### Notes on Animations:

*   All listed animations (`stand`, `walk`, `run`, `burn`) share the same frame dimensions and timing.
*   The `run` and `burn` animations are explicitly noted as being copied from the `walk` animation, suggesting they use the same visual sequence.
*   `loop="1"` indicates that each animation will repeat indefinitely once started.
*   The sprite sheet (`weakspirit.png`) is assumed to contain 6 frames arranged in a single row, each 18x18 pixels.