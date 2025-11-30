---
title: Big Firebug Emissive Sprite Animations
category: entities
---

# Big Firebug Emissive Sprite Animations

This document details the sprite animations for the Big Firebug's emissive texture, used for its glowing effects.

## Sprite Definition

The main `<Sprite>` tag defines the base properties for the sprite sheet.

### Key Attributes:

*   **filename**: `data/enemies_gfx/bigfirebug_emissive.png` - The path to the sprite sheet image.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `18` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations within the sprite sheet. Each animation specifies how to extract frames from the image and how they should be played.

### Common Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "burn").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **pos\_x**: The horizontal starting position of the animation frames on the sprite sheet (in pixels).
*   **pos\_y**: The vertical starting position of the animation frames on the sprite sheet (in pixels).

### Defined Animations:

| Animation Name   | Frame Count | Frame Size (WxH) | Frames Per Row | Frame Wait | Position (X, Y) | Loop | Notes                               |
| :--------------- | :---------- | :--------------- | :------------- | :--------- | :-------------- | :--- | :---------------------------------- |
| `stand`          | 10          | 20x20            | 10             | 0.05       | (0, 1)          | Yes  | Standard idle animation.            |
| `walk`           | 10          | 20x20            | 10             | 0.05       | (0, 1)          | Yes  | Walking animation.                  |
| `run`            | 10          | 20x20            | 10             | 0.05       | (0, 1)          | Yes  | Running animation.                  |
| `burn`           | 10          | 20x20            | 10             | 0.05       | (0, 1)          | Yes  | Animation when burning.             |
| `fly_move`       | 8           | 20x20            | 8              | 0.035      | (0, 22)         | Yes  | Flying movement animation.          |
| `fly_idle`       | 8           | 20x20            | 8              | 0.035      | (0, 22)         | Yes  | Flying idle animation.              |
| `attack_dash`    | 8           | 20x20            | 8              | 0.035      | (0, 22)         | Yes  | Dash attack animation.              |
| `attack_ranged`  | 8           | 21x21            | 8              | 0.06       | (0, 43)         | No   | Ranged attack animation. `shrink_by_one_pixel="1"` applied. |

**Note:** Animations `stand`, `walk`, `run`, and `burn` share the same frame dimensions and starting position, suggesting they might be part of the same sprite row. `fly_move`, `fly_idle`, and `attack_dash` share another set of properties. `attack_ranged` has slightly different dimensions and a specific `loop="0"` attribute, indicating it's a non-looping animation.