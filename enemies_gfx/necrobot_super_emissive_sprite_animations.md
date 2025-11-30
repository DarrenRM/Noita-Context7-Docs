---
title: Necrobot Super Emissive Sprite Animations
category: enemies_gfx
---

# Necrobot Super Emissive Sprite Animations

This document details the sprite animations for the "Necrobot Super Emissive" enemy in Noita, as defined in the `necrobot_super_emissive.xml` file. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base properties of the enemy's visual representation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/necrobot_super_emissive.png` - The path to the sprite sheet image.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `22` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation state for the enemy.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**: The X-coordinate on the sprite sheet where the animation frames begin.
*   **pos\_y**: The Y-coordinate on the sprite sheet where the animation frames begin.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are present horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping animations.

### Animation Breakdown:

| Animation Name   | Description        | Frame Count | Frame Wait | Loop | Key Events                                                              |
| :--------------- | :----------------- | :---------- | :--------- | :--- | :---------------------------------------------------------------------- |
| `stand`          | Idle animation     | 6           | 0.2        | 1    | None                                                                    |
| `walk`           | Walking animation  | 4           | 0.082      | 1    | None                                                                    |
| `run`            | Fake run (copy of walk) | 4           | 0.082      | 1    | None                                                                    |
| `burn`           | Fake burn (copy of walk) | 4           | 0.06       | 1    | `step` (frame 2 & 5)                                                    |
| `jump_up`        | Jumping upwards    | 1           | 0.082      | 0    | `jump` (frame 0)                                                        |
| `jump_fall`      | Falling after jump | 1           | 0.082      | 0    | None                                                                    |
| `attack_ranged`  | Ranged attack      | 10          | 0.09       | 0    | `shoot_bullet` (frame 5)                                                |
| `fly_idle`       | Hovering animation | 4           | 0.12       | 1    | None                                                                    |
| `fly_move`       | Flying animation   | 4           | 0.09       | 1    | None                                                                    |
| `attack`         | Melee attack       | 10          | 0.09       | 0    | `hit` (frame 5)                                                         |

### Animation Event Details:

Events within `<RectAnimation>` tags trigger specific actions at certain frames.

*   **`step`**: Triggered during the `burn` animation. `check_physics_material="1"` suggests it might react to the ground material.
*   **`jump`**: Triggered at the start of the `jump_up` animation. `check_physics_material="1"` indicates it might be influenced by the environment.
*   **`shoot_bullet`**: Triggered during the `attack_ranged` animation. `check_physics_material="0"` implies it's not dependent on the ground material.
*   **`hit`**: Triggered during the `attack` animation. `check_physics_material="0"` suggests it's not dependent on the ground material.