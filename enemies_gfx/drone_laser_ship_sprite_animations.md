---
title: Drone Laser Ship Sprite Animations
category: data/enemies_gfx/
---

# Drone Laser Ship Sprite Animations

This document details the sprite animations for the Drone Laser Ship enemy in Noita, as defined in the `drone_lasership.xml` file. It focuses on the key attributes of each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/drone_lasership.png` - The primary image file for the sprite.
*   **offset\_x**: `22` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation state that plays by default.

## Animation States

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation state for the Drone Laser Ship.

### Common Attributes for `RectAnimation`:

*   **name**: The identifier for the animation state (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: The total number of frames in the animation.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frame\_height**: The height of a single frame in pixels.
*   **frame\_width**: The width of a single frame in pixels.
*   **pos\_x**: The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames within the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.

### Defined Animation States:

| Animation Name   | Frame Count | Frames Per Row | Frame Wait | Frame Height | Frame Width | Pos X | Pos Y | Loop | Key Events                                                              |
| :--------------- | :---------- | :------------- | :--------- | :----------- | :---------- | :---- | :---- | :--- | :---------------------------------------------------------------------- |
| **stand**        | 5           | 5              | 0.09       | 22           | 38          | 0     | 0     | 1    | None                                                                    |
| **walk**         | 5           | 5              | 0.09       | 22           | 38          | 0     | 0     | 1    | None                                                                    |
| **fly\_move**    | 5           | 5              | 0.09       | 22           | 38          | 0     | 22    | 1    | None                                                                    |
| **fly\_idle**    | 5           | 5              | 0.09       | 22           | 38          | 0     | 0     | 1    | None                                                                    |
| **attack\_ranged** | 10          | 10             | 0.12       | 22           | 38          | 0     | 44    | 0    | Frame 1: `open` (probability 1, check\_physics\_material 0) |

**Note:** The `stand` and `fly_idle` animations share the same sprite sheet coordinates (`pos_x="0"`, `pos_y="0"`), suggesting they might use the same visual frames. The `attack_ranged` animation is non-looping and triggers an `open` event on its first frame.