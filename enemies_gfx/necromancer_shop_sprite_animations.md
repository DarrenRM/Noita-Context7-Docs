---
title: Necromancer Shop Sprite Animations
category: enemies_gfx
---

# Necromancer Shop Sprite Animations

This document details the sprite animations for the Necromancer Shop entity in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/necromancer_shop.png` - The path to the sprite sheet.
*   **offset\_x**: `13` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `24` - Vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations.

### Common Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each individual frame.
*   **frame\_height**: Height of each individual frame.
*   **frames\_per\_row**: How many frames are present in a single row of the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (typically for attack animations).

### Specific Animations:

| Animation Name      | Frame Count | Frame Size (WxH) | Frames Per Row | Frame Wait | Loop | Notes                               |
| :------------------ | :---------- | :--------------- | :------------- | :--------- | :--- | :---------------------------------- |
| `stand`             | 6           | 32x32            | 6              | 0.1        | Yes  | Idle standing animation.            |
| `walk`              | 6           | 32x32            | 6              | 0.085      | Yes  | Walking animation.                  |
| `run`               | 6           | 32x32            | 6              | 0.085      | Yes  | Running animation.                  |
| `burn`              | 6           | 32x32            | 6              | 0.085      | Yes  | Burning animation.                  |
| `fly_idle`          | 6           | 32x32            | 15             | 0.12       | Yes  | Idle flying animation.              |
| `fly_move`          | 6           | 32x32            | 15             | 0.12       | Yes  | Moving while flying animation.      |
| `attack_ranged`     | 8           | 33x33            | 8              | 0.04       | No   | Ranged attack animation.            |
| `attack_ranged_fast`| 7           | 33x33            | 8              | 0.01       | No   | Faster ranged attack animation.     |

## Animation Events

The `<Event>` tag within `<RectAnimation>` defines actions that occur at specific frames.

### Key Attributes:

*   **name**: The name of the event (e.g., "shoot\_magic").
*   **frame**: The frame number (0-indexed) at which the event triggers.
*   **probability**: The chance (0 to 1) of the event occurring.
*   **max\_distance**: Maximum distance for the event to trigger (relevant for projectiles).
*   **check\_physics\_material**: Whether to check physics material for the event.
*   **on\_finished**: Whether the event should trigger when the animation finishes.

### Specific Events:

*   **`attack_ranged` / `attack_ranged_fast`**:
    *   **Event Name**: `shoot_magic`
    *   **Trigger Frame**: `3`
    *   **Probability**: `1` (always triggers)
    *   **Max Distance**: `500`
    *   **Check Physics Material**: `0` (disabled)
    *   **On Finished**: `0` (does not trigger on animation end)

This event is responsible for the Necromancer Shop firing its magical projectiles.