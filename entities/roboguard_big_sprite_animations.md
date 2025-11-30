---
title: Roboguard Big Sprite Animations
category: entities
---

# Roboguard Big Sprite Animations

This document details the sprite animations for the "roboguard_big" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite 
  filename="data/enemies_gfx/roboguard_big.png" 
  offset_x="9" 
  offset_y="16"
  default_animation="stand" >
  <!-- Animation definitions go here -->
</Sprite>
```

*   **filename**: Path to the sprite sheet.
*   **offset_x**, **offset_y**: Adjusts the sprite's position relative to its origin.
*   **default_animation**: The animation to play when no other is specified.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `RectAnimation`

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame_count**: Total number of frames in the animation.
*   **frame_width**, **frame_height**: Dimensions of each individual frame.
*   **frames_per_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame_wait**: Duration (in seconds) each frame is displayed.
*   **pos_x**, **pos_y**: The starting coordinates of the animation frames on the sprite sheet.
*   **loop**: `0` for non-looping animations, `1` (or omitted) for looping.
*   **shrink_by_one_pixel**: A common attribute for adjusting sprite dimensions.

### Animation Breakdown

| Animation Name   | Frame Count | Frame Size (W x H) | Frames Per Row | Frame Wait (s) | Loop | Key Events                               | Notes                                  |
| :--------------- | :---------- | :----------------- | :------------- | :------------- | :--- | :--------------------------------------- | :------------------------------------- |
| **stand**        | 6           | 24 x 20            | 6              | 0.12           | Yes  | None                                     | Default idle animation.                |
| **walk**         | 6           | 25 x 21            | 6              | 0.12           | Yes  | `step` (frame 2, 5)                      | Standard walking animation.            |
| **run**          | 6           | 25 x 21            | 8              | 0.09           | Yes  | `step` (frame 2, 5)                      | Faster movement, shorter frame wait.   |
| **burn**         | 6           | 25 x 21            | 8              | 0.09           | Yes  | `step` (frame 2, 5)                      | Similar to run, likely for burning state. |
| **jump_up**      | 1           | 24 x 20            | 8              | 0.082          | No   | `jump` (frame 0)                         | Single frame for initiating jump.      |
| **jump_fall**    | 1           | 24 x 20            | 8              | 0.082          | No   | None                                     | Single frame for falling after jump.   |
| **attack**       | 5           | 25 x 21            | 8              | 0.08           | No   | `hit` (frame 3)                          | Melee attack animation.                |
| **attack_ranged**| 6           | 25 x 21            | 8              | 0.08           | No   | `shoot_bullet` (frame 2)                 | Ranged attack animation.               |
| **land**         | 4           | 25 x 21            | 8              | 0.1            | No   | None                                     | Animation played upon landing.         |
| **hurt**         | 2           | 25 x 21            | 8              | 0.11           | No   | None                                     | Reaction animation to taking damage.   |

### Animation Events

Events trigger specific game actions at certain frames within an animation.

*   **name**: The type of event (e.g., "step", "jump", "hit", "shoot_bullet").
*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **check_physics_material**: If `1`, the event might depend on the ground material.
*   **probability**: Likelihood of the event triggering (usually `1`).
*   **max_distance**: Maximum distance for certain event checks.
*   **on_finished**: `0` indicates the event doesn't stop the animation.

This structured documentation should help AI models understand and potentially modify the animation behavior of the Roboguard Big enemy.