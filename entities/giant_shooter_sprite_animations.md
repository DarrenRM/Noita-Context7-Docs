---
title: Giant Shooter Sprite Animations
category: entities
---

# Giant Shooter Sprite Animations

This document details the sprite animations for the "Giant Shooter" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/giantshooter.png` - The primary image file for the enemy.
*   **offset\_x**: `10` - Horizontal offset of the sprite.
*   **offset\_y**: `16` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation played by default when the enemy is idle.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **shrink\_by\_one\_pixel**: A value indicating if frames should be shrunk by one pixel (often `1` for adjustments).
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.

### Animation Details:

| Animation Name    | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Loop | Key Events                               |
| :---------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :--- | :--------------------------------------- |
| `stand`           | 4           | 21          | 33           | 6              | 0.25       | 0     | 1     | Yes  | None                                     |
| `walk`            | 4           | 21          | 33           | 6              | 0.25       | 0     | 1     | Yes  | None                                     |
| `run`             | 4           | 21          | 33           | 6              | 0.25       | 0     | 1     | Yes  | None                                     |
| `burn`            | 4           | 21          | 33           | 6              | 0.25       | 0     | 1     | Yes  | None                                     |
| `attack_ranged`   | 4           | 21          | 33           | 6              | 0.25       | 0     | 1     | Yes  | Frame 0: `attack_bite` (probability 1) |
| `attack`          | 4           | 21          | 33           | 4              | 0.09       | 0     | 34    | No   | Frame 0: `attack_bite` (probability 1) |

### Event Details:

*   **`<Event>`**: Triggers an action at a specific frame.
    *   **frame**: The frame number (0-indexed) at which the event occurs.
    *   **name**: The name of the event to trigger (e.g., `attack_bite`).
    *   **on\_finished**: If `0`, the event is triggered once. If `1`, it's triggered when the animation finishes.
    *   **probability**: The chance (0 to 1) that the event will occur.

**Note:** The `attack` animation uses a different `pos_y` and `frame_wait` compared to other animations, suggesting it's a distinct visual sequence. The `attack_ranged` and `attack` animations both trigger an `attack_bite` event on their first frame.