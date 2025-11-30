---
title: Assassin Emissive Sprite Animations
category: entities/enemies_gfx
---

# Assassin Emissive Sprite Animations

This document details the sprite animations for the Assassin enemy, specifically its "emissive" variant. It outlines the key frames, timings, and layout for each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/assassin_emissive.png` - The texture file containing all animation frames.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation States

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes:

*   **name**: The identifier for the animation state (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet for this animation.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **pos\_x**: The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; otherwise, it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates a slight shrinking effect applied to frames.

### Animation Breakdown:

| Animation Name   | Frame Count | Frame Size (WxH) | Frame Wait (s) | Frames Per Row | Y Position | Loop | Notes                               |
| :--------------- | :---------- | :--------------- | :------------- | :------------- | :--------- | :--- | :---------------------------------- |
| **stand**        | 6           | 18x16            | 0.1            | 6              | 1          | Yes  | Idle animation.                     |
| **walk**         | 6           | 18x16            | 0.085          | 6              | 18         | Yes  | Movement animation.                 |
| **run**          | 6           | 18x16            | 0.085          | 6              | 18         | Yes  | Faster movement animation.          |
| **burn**         | 6           | 18x16            | 0.085          | 6              | 18         | Yes  | Animation for being on fire.        |
| **jump\_up**     | 2           | 18x16            | 0.1            | 6              | 35         | No   | Ascending phase of a jump.          |
| **jump\_fall**   | 2           | 18x16            | 0.1            | 6              | 52         | No   | Descending phase of a jump.         |
| **land**         | 3           | 18x16            | 0.1            | 6              | 69         | No   | Animation upon landing.             |
| **attack**       | 5           | 19x17            | 0.08           | 6              | 86         | No   | Standard attack animation.          |
| **hurt**         | 2           | 18x16            | 0.12           | 6              | 103        | No   | Reaction to taking damage.          |
| **attack\_dash** | 15          | 18x16            | 0.055          | 15             | 120        | No   | A quick dashing attack.             |
| **fly\_idle**    | 4           | 18x16            | 0.09           | 15             | 137        | Yes  | Stationary flying animation.        |
| **fly\_move**    | 4           | 18x16            | 0.09           | 15             | 137        | Yes  | Moving while flying.                |

**Note:** Animations like "walk", "run", "burn", "fly\_idle", and "fly\_move" share the same `pos_y` and `frame_width`/`frame_height`, suggesting they might be visually similar or use a common sprite strip segment. The `frames_per_row` differs for `attack_dash` and `fly_` animations, indicating a different layout within the sprite sheet.