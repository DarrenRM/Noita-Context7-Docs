---
title: Basebot Hidden Emissive Sprite Animations
category: data/enemies_gfx
---

# Basebot Hidden Emissive Sprite Animations

This document details the sprite animations for the "basebot_hidden_emissive" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/basebot_hidden_emissive.png"
 offset_x="9"
 offset_y="15"
 default_animation="stand" >
```

*   **`filename`**: Path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: The animation that plays when no other animation is specified.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `RectAnimation`

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "attack"). This is crucial for triggering animations via scripts.
*   **`pos_x`**, **`pos_y`**: The starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet. This helps calculate the position of subsequent frames.
*   **`loop`**: `1` for looping animations, `0` for one-time animations.

### Animation Breakdown

| Animation Name   | Description                               | `frame_count` | `frame_wait` | `loop` | Notes                                       |
| :--------------- | :---------------------------------------- | :------------ | :----------- | :----- | :------------------------------------------ |
| `stand`          | Idle animation                            | 6             | 0.12         | 1      |                                             |
| `walk`           | Walking animation                         | 4             | 0.09         | 1      |                                             |
| `run`            | Running animation (copy of walk)          | 4             | 0.09         | 1      | Currently identical to `walk`.              |
| `burn`           | Burning animation (copy of walk)          | 4             | 0.09         | 1      | Currently identical to `walk`.              |
| `attack`         | Melee attack animation                    | 5             | 0.05         | 0      |                                             |
| `attack_ranged`  | Ranged attack animation                   | 5             | 0.05         | 0      | Currently identical to `attack`.            |
| `fly_idle`       | Flying idle animation                     | 6             | 0.085        | 1      |                                             |
| `fly_move`       | Flying movement animation                 | 4             | 0.07         | 1      |                                             |

**Note:** Animations like `run`, `burn`, and `attack_ranged` are currently identical to other animations (`walk` and `attack` respectively). Modders can modify these to create distinct visual effects.

This XML file defines the visual representation and animation cycles for the "basebot_hidden_emissive" enemy. Understanding these attributes is key to customizing its appearance or behavior through modding.