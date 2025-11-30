---
title: Tank Super Emissive Sprite Animations
category: enemies_gfx
---

# Tank Super Emissive Sprite Animations

This document details the sprite animations for the "tank_super_emissive" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/tank_super_emissive.png` - The primary image file for this enemy.
*   **offset\_x**: `9` - Horizontal offset for the sprite.
*   **offset\_y**: `17` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations. Each animation is a sequence of frames extracted from the sprite sheet.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **pos\_x**: The starting X-coordinate of the animation frames on the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; `1` (or omitted) indicates it loops.

### Animation Breakdown:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Pos X | Pos Y | Loop | Notes                               |
| :--------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :---- | :---- | :--- | :---------------------------------- |
| `stand`          | 1           | 22          | 20           | 0.16       | 11             | 0     | 0     | Yes  | Idle animation.                     |
| `walk`           | 4           | 22          | 20           | 0.1        | 11             | 0     | 20    | Yes  | Movement animation.                 |
| `run`            | 4           | 22          | 20           | 0.09       | 11             | 0     | 20    | Yes  | Faster movement animation.          |
| `burn`           | 4           | 22          | 20           | 0.09       | 11             | 0     | 20    | Yes  | Animation when burning.             |
| `attack`         | 4           | 22          | 20           | 0.07       | 11             | 0     | 40    | No   | Melee attack animation.             |
| `attack_ranged`  | 4           | 22          | 20           | 0.07       | 11             | 0     | 40    | No   | Ranged attack animation.            |
| `attack_grenade` | 11          | 22          | 20           | 0.04       | 11             | 0     | 60    | No   | Grenade throwing animation.         |

**Note:** The `walk`, `run`, and `burn` animations share the same `pos_y` (20) and `frames_per_row` (11), implying they are likely contiguous frames within the sprite sheet, differentiated by their `frame_count` and `frame_wait`. Similarly, `attack` and `attack_ranged` share `pos_y` (40).