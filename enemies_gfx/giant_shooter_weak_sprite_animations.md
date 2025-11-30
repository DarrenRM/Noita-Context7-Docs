---
title: Giant Shooter (Weak) Sprite Animations
category: enemies_gfx
---

# Giant Shooter (Weak) Sprite Animations

This document details the sprite animations for the "Giant Shooter (Weak)" enemy in Noita, as defined in its XML configuration file. It focuses on the key attributes of the sprite and its associated animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the enemy.

### Key Attributes:

*   **filename**: `data/enemies_gfx/giantshooter_weak.png` - The path to the sprite sheet image.
*   **offset\_x**: `10` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `16` - Vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## RectAnimation Definitions

The `<RectAnimation>` tags define individual animation sequences. Each animation is composed of frames from the sprite sheet.

### Common Attributes for Animations:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **shrink\_by\_one\_pixel**: A flag indicating if frames should be shrunk by one pixel (often for visual consistency).
*   **loop**: (Optional) If set to `0`, the animation does not loop. Defaults to looping.

### Defined Animations:

| Animation Name     | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Pos X | Pos Y | Shrink | Loop | Events                               |
| :----------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :---- | :---- | :----- | :--- | :----------------------------------- |
| **stand**          | 4           | 21          | 33           | 0.25       | 6              | 0     | 1     | 1      | Yes  | None                                 |
| **walk**           | 4           | 21          | 33           | 0.25       | 6              | 0     | 1     | 1      | Yes  | None                                 |
| **run**            | 4           | 21          | 33           | 0.25       | 6              | 0     | 1     | 1      | Yes  | None                                 |
| **burn**           | 4           | 21          | 33           | 0.25       | 6              | 0     | 1     | 1      | Yes  | None                                 |
| **attack\_ranged** | 4           | 21          | 33           | 0.25       | 6              | 0     | 1     | 1      | Yes  | `attack_bite` at frame 0             |
| **attack**         | 4           | 21          | 33           | 0.09       | 4              | 0     | 34    | 1      | No   | `attack_bite` at frame 0             |

### Animation Events:

`<Event>` tags within an animation define specific actions or triggers that occur at certain frames.

*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **name**: The name of the event (e.g., "attack\_bite").
*   **on\_finished**: (Optional) If set to `1`, the event triggers when the animation finishes.
*   **probability**: (Optional) The probability (0-1) of the event occurring.

**Note:** The `attack_ranged` and `attack` animations both have an `attack_bite` event at frame 0. The `attack` animation has a faster frame wait (`0.09`) and does not loop, suggesting it's a distinct, shorter attack sequence.