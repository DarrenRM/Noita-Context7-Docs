---
title: Necrobot Emissive Sprite Animations
category: data/enemies_gfx
---

---

# Necrobot Emissive Sprite Animations

This document details the sprite animations for the Necrobot enemy, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offsets.

### Key Attributes:

*   **filename**: `data/enemies_gfx/necrobot_emissive.png` - Path to the sprite sheet.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `22` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**: The starting X coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are present horizontally in the sprite sheet row.
*   **loop**: `1` for looping animations, `0` for non-looping.

### Animation Breakdown:

| Animation Name   | `pos_y` | `frame_count` | `frame_wait` | `loop` | Key Events                                                              | Notes                                     |
| :--------------- | :------ | :------------ | :----------- | :----- | :---------------------------------------------------------------------- | :---------------------------------------- |
| `stand`          | `0`     | `6`           | `0.2`        | `1`    | None                                                                    | Default idle animation.                   |
| `walk`           | `30`    | `4`           | `0.082`      | `1`    | None                                                                    | Standard walking animation.               |
| `run`            | `30`    | `4`           | `0.082`      | `1`    | None                                                                    | Identical to `walk`.                      |
| `burn`           | `30`    | `4`           | `0.06`       | `1`    | `frame="2" name="step"`, `frame="5" name="step"`                        | Burning animation with "step" events.     |
| `jump_up`        | `60`    | `1`           | `0.082`      | `0`    | `frame="0" name="jump"`                                                 | Single frame for jumping upwards.         |
| `jump_fall`      | `60`    | `1`           | `0.082`      | `0`    | None                                                                    | Single frame for falling after jump.      |
| `attack_ranged`  | `150`   | `10`          | `0.09`       | `0`    | `frame="5" name="shoot_bullet"`                                         | Ranged attack animation.                  |
| `fly_idle`       | `90`    | `4`           | `0.12`       | `1`    | None                                                                    | Idle animation while flying.              |
| `fly_move`       | `120`   | `4`           | `0.09`       | `1`    | None                                                                    | Movement animation while flying.          |
| `attack`         | `150`   | `10`          | `0.09`       | `0`    | `frame="5" name="hit"`                                                  | Melee attack animation with "hit" event.  |

### Animation Events:

Some animations include `<Event>` tags, which trigger specific game actions at certain frames.

*   **frame**: The frame number at which the event occurs.
*   **name**: The name of the event (e.g., "step", "jump", "shoot\_bullet", "hit").
*   **probability**: The likelihood of the event occurring (usually `1` for guaranteed events).
*   **check\_physics\_material**: Whether to check the physics material of the current tile for the event.

**Example Event:**

```xml
<Event frame="5" name="shoot_bullet" probability="1" check_physics_material="0"/>
```
This event triggers a "shoot\_bullet" action on frame 5 of the `attack_ranged` animation, without checking the physics material.