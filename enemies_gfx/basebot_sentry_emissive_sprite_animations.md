---
title: Basebot Sentry Emissive Sprite Animations
category: enemies_gfx
---

# Basebot Sentry Emissive Sprite Animations

This document details the sprite animations for the "basebot_sentry_emissive" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/basebot_sentry_emissive.png"
 offset_x="9"
 offset_y="15"
 default_animation="stand" >
</Sprite>
```

*   **`filename`**: Path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: Specifies the animation to play when the sprite is first loaded or when no other animation is active.

## Animation Definitions

The `<RectAnimation>` tags define individual animations. Each animation is a sequence of frames extracted from the sprite sheet.

### Key Animation Attributes

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `name`           | The identifier for the animation (e.g., "stand", "walk", "attack").         |
| `pos_x`          | The X-coordinate of the top-left corner of the animation frames on the sheet. |
| `pos_y`          | The Y-coordinate of the top-left corner of the animation frames on the sheet. |
| `frame_count`    | The total number of frames in this animation.                               |
| `frame_width`    | The width of each individual frame in pixels.                               |
| `frame_height`   | The height of each individual frame in pixels.                              |
| `frame_wait`     | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row` | How many frames are arranged horizontally on the sprite sheet.              |
| `loop`           | `1` for looping animations, `0` for non-looping animations.                 |

### Defined Animations

| Animation Name   | `pos_y` | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `loop` | Notes                               |
| :--------------- | :------ | :------------ | :------------ | :------------- | :----------- | :----- | :---------------------------------- |
| `stand`          | `0`     | `6`           | `20`          | `20`           | `0.12`       | `1`    | Default idle animation.             |
| `walk`           | `20`    | `4`           | `20`          | `20`           | `0.09`       | `1`    | Movement animation.                 |
| `run`            | `20`    | `4`           | `20`          | `20`           | `0.09`       | `1`    | Copied from `walk`.                 |
| `burn`           | `20`    | `4`           | `20`          | `20`           | `0.09`       | `1`    | Copied from `walk`.                 |
| `attack`         | `40`    | `5`           | `20`          | `20`           | `0.05`       | `0`    | Attack animation.                   |
| `attack_ranged`  | `40`    | `5`           | `20`          | `20`           | `0.05`       | `0`    | Ranged attack animation (same as attack). |
| `fly_idle`       | `0`     | `6`           | `20`          | `20`           | `0.085`      | `1`    | Flying idle animation.              |
| `fly_move`       | `20`    | `4`           | `20`          | `20`           | `0.07`       | `1`    | Flying movement animation.          |

**Note:** The `run`, `burn`, and `attack_ranged` animations are currently identical to `walk` and `attack` respectively, suggesting they might be placeholders or intended for future differentiation.