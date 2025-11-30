---
title: Tank Enemy Sprite Animations
category: data/enemies_gfx
---

# Tank Enemy Sprite Animations

This document details the sprite animations for the "Tank" enemy in Noita, as defined in `tank.xml`. It focuses on the key attributes of each animation, providing a concise overview for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base properties for the enemy's visual representation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/tank.png` - The path to the sprite sheet image.
*   **offset\_x**: `9` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` elements, each defining a distinct animation.

### Animation Breakdown:

| Animation Name   | Description                               | Frame Count | Frame Width | Frame Height | Frame Wait | Loop | Notes                                                              |
| :--------------- | :---------------------------------------- | :---------- | :---------- | :----------- | :--------- | :--- | :----------------------------------------------------------------- |
| `stand`          | Idle animation.                           | 1           | 22          | 20           | 0.16       | 1    | Single frame, likely a static pose.                                |
| `walk`           | Walking animation.                        | 4           | 22          | 20           | 0.1        | 1    | Standard walking cycle.                                            |
| `run`            | Running animation.                        | 4           | 22          | 20           | 0.09       | 1    | Faster than `walk`, copied from `walk` with reduced frame wait.    |
| `burn`           | Burning animation.                        | 4           | 22          | 20           | 0.09       | 1    | Visual effect for being on fire, copied from `walk`.               |
| `attack`         | Primary attack animation (shooting bullet). | 4           | 22          | 20           | 0.07       | 0    | Fires bullets on frames 1 and 3.                                   |
| `attack_ranged`  | Ranged attack animation (shooting bullet).  | 4           | 22          | 20           | 0.07       | 0    | Identical to `attack`, fires bullets on frames 1 and 3.            |
| `attack_grenade` | Grenade attack animation.                 | 11          | 22          | 20           | 0.04       | 0    | Fires a projectile on frame 8.                                       |

### Key Animation Attributes:

*   **name**: The identifier for the animation.
*   **pos\_x**, **pos\_y**: The starting coordinates of the animation frames on the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for one-off animations.

### Animation Events:

Animations can trigger specific game events at certain frames.

*   **`attack` / `attack_ranged`**:
    *   **frame 1**: `shoot_bullet` event.
    *   **frame 3**: `shoot_bullet` event.
*   **`attack_grenade`**:
    *   **frame 8**: `shoot_bullet` event.

These events are crucial for understanding when and how the enemy performs actions like firing projectiles. The `probability` and `check_physics_material` attributes are set to `1` and `0` respectively, indicating these events are guaranteed to trigger and do not depend on physics material checks.