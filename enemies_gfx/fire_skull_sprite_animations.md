---
title: Fire Skull Sprite Animations
category: enemies_gfx
---

# Fire Skull Sprite Animations

This document details the sprite animations for the Fire Skull enemy in Noita, as defined in `fireskull.xml`. It focuses on the key attributes of the sprite and its associated animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and its positioning.

*   **filename**: `data/enemies_gfx/fireskull.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `10` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations. Each animation uses a portion of the sprite sheet.

### Common Animation Attributes

Most animations share these core properties:

*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **pos\_x**: The X-coordinate on the sprite sheet where the animation frames begin.
*   **pos\_y**: The Y-coordinate on the sprite sheet where the animation frames begin.

### Specific Animations

| Animation Name    | Frame Count | Frame Height | Frame Width | Frames Per Row | Frame Wait | Loop | Notes                                     |
| :---------------- | :---------- | :----------- | :---------- | :------------- | :--------- | :--- | :---------------------------------------- |
| **stand**         | 6           | 20           | 16          | 6              | 0.09       | Yes  | Idle animation.                           |
| **walk**          | 6           | 20           | 16          | 6              | 0.09       | Yes  | Walking animation.                        |
| **run**           | 6           | 20           | 16          | 6              | 0.09       | Yes  | Running animation.                        |
| **burn**          | 6           | 20           | 16          | 6              | 0.09       | Yes  | Animation for when the enemy is burning.  |
| **attack**        | 5           | 20           | 16          | 6              | 0.08       | No   | Melee attack animation.                   |
| **attack\_ranged**| 5           | 20           | 16          | 6              | 0.08       | No   | Ranged attack animation.                  |
| **attack\_dash**  | 5           | 20           | 16          | 6              | 0.07       | No   | Dash attack animation.                    |

### Animation Events

Some animations can trigger events at specific frames.

#### `attack` and `attack_ranged` Animations

*   **Event Name**: `bite`
*   **Frame**: `3`
*   **Probability**: `1`
*   **Description**: Triggers a "bite" action. `check_physics_material` and `max_distance` are also defined but are less critical for basic animation understanding.

#### `attack_dash` Animation

*   **Event Name**: `dash`
*   **Frame**: `0`
*   **Probability**: `1`
*   **Description**: Triggers a "dash" action.