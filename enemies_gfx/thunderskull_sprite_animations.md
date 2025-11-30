---
title: Thunderskull Sprite Animations
category: enemies_gfx
---

# Thunderskull Sprite Animations

This document details the sprite animations for the Thunderskull enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main sprite definition for the Thunderskull.

### Key Attributes:

*   **filename**: `data/enemies_gfx/thunderskull.png` - The path to the sprite sheet.
*   **offset_x**: `8` - Horizontal offset for the sprite.
*   **offset_y**: `13` - Vertical offset for the sprite.
*   **default_animation**: `"stand"` - The animation that plays by default.

## Animations

The Thunderskull has several distinct animations, each defined by a `RectAnimation` tag.

### Animation Details:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Frames Per Row | Loop | Events                                                              |
| :--------------- | :---------- | :---------- | :----------- | :------------- | :------------- | :--- | :------------------------------------------------------------------ |
| `stand`          | 5           | 16          | 16           | 0.13           | 5              | 1    | None                                                                |
| `walk`           | 5           | 16          | 16           | 0.11           | 5              | 1    | None                                                                |
| `run`            | 5           | 16          | 16           | 0.09           | 5              | 1    | None                                                                |
| `burn`           | 5           | 16          | 16           | 0.09           | 5              | 1    | None                                                                |
| `attack`         | 5           | 16          | 16           | 0.08           | 6              | 0    | Frame 1: `attack_bite`                                              |
| `attack_ranged`  | 5           | 16          | 16           | 0.08           | 6              | 0    | Frame 2: `attack_shoot`                                             |
| `attack_dash`    | 5           | 16          | 16           | 0.07           | 6              | 0    | Frame 0: `attack_dash`                                              |

### Key Attributes for Animations:

*   **name**: The identifier for the animation (e.g., `stand`, `attack`).
*   **pos_x**, **pos_y**: The starting position of the animation frames within the sprite sheet (always `0,0` for these animations).
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.
*   **Event**: Triggers specific game events at certain frames.
    *   **frame**: The frame number at which the event occurs.
    *   **name**: The name of the event to trigger (e.g., `attack_bite`, `attack_shoot`).
    *   **probability**: The chance of the event occurring (usually `1` for guaranteed events).
    *   **check\_physics\_material**: Whether physics material checks are performed for this event (usually `0`).