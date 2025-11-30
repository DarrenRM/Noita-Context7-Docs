---
title: Tank Rocket Sprite Animations
category: data/enemies_gfx
---

# Tank Rocket Sprite Animations

This document details the sprite animations for the "Tank Rocket" enemy in Noita, as defined in the `tank_rocket.xml` file. This information is crucial for understanding and modifying the visual behavior of this enemy.

## Sprite Definition

The primary sprite for the Tank Rocket is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/tank_rocket.png` - Specifies the image file containing all animation frames.
*   **offset\_x**: `9` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation state.

### Animation States:

| Animation Name | Description                               | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Frames Per Row | Loop | Event                                                              |
| :------------- | :---------------------------------------- | :---------- | :---------- | :----------- | :------------- | :------------- | :--- | :----------------------------------------------------------------- |
| `stand`        | Idle animation.                           | 1           | 22          | 20           | 0.16           | 4              | 1    | None                                                               |
| `walk`         | Walking animation.                        | 4           | 22          | 20           | 0.1            | 4              | 1    | None                                                               |
| `run`          | Running animation (copied from walk).     | 4           | 22          | 20           | 0.09           | 4              | 1    | None                                                               |
| `burn`         | Burning animation (copied from walk).     | 4           | 22          | 20           | 0.09           | 4              | 1    | None                                                               |
| `attack`       | Attack animation (fires a rocket).        | 4           | 22          | 20           | 0.07           | 4              | 0    | `shoot_rocket` on frame 1                                          |
| `attack_ranged`| Ranged attack animation (fires a rocket). | 4           | 22          | 20           | 0.07           | 4              | 0    | `shoot_rocket` on frame 1                                          |

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation state (e.g., `stand`, `walk`, `attack`).
*   **pos\_x**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual animation frame.
*   **frame\_height**: The height of each individual animation frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping animations.
*   **Event**: Triggers specific game events at certain frames.
    *   **name**: The name of the event to trigger (e.g., `shoot_rocket`).
    *   **frame**: The frame number on which to trigger the event.
    *   **probability**: The chance of the event occurring (usually `1` for guaranteed events).
    *   **check\_physics\_material**: Whether to check physics materials when triggering the event.

## Notes for Modding:

*   The `run` and `burn` animations are direct copies of the `walk` animation. Modifying `walk` will affect these as well unless they are explicitly changed.
*   Both `attack` and `attack_ranged` animations are identical and trigger the `shoot_rocket` event on their first frame. This suggests they are functionally the same for triggering the projectile.
*   The `shoot_rocket` event is crucial for understanding when and how the Tank Rocket fires its projectiles.
*   Adjusting `frame_wait` values will alter the speed of animations. Lower values make animations faster.
*   Modifying `frame_count`, `frame_width`, and `frame_height` requires careful consideration of the sprite sheet layout.
*   The `pos_y` attribute is used to select different rows of animations from the sprite sheet.