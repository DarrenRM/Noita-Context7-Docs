---
title: Firebug Sprite Animations
category: entities
---

# Firebug Sprite Animations

This document details the sprite animations for the "firebug" enemy in Noita, as defined in its XML configuration file. This information is crucial for understanding and modifying the visual behavior of this enemy.

## Sprite Definition

The primary sprite for the firebug is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/firebug.png` - Specifies the image file containing the sprite frames.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `13` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation.

### General Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_dash").
*   **pos\_x**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` for looping animations, `0` for non-looping animations.

### Specific Animations:

| Animation Name   | Description        | `pos_y` | `frame_count` | `frame_wait` | `loop` | Key Events                                                              |
| :--------------- | :----------------- | :------ | :------------ | :----------- | :----- | :---------------------------------------------------------------------- |
| `stand`          | Idle animation     | `0`     | `10`          | `0.05`       | `1`    | None                                                                    |
| `walk`           | Walking animation  | `0`     | `10`          | `0.05`       | `1`    | None                                                                    |
| `run`            | Running animation  | `0`     | `10`          | `0.05`       | `1`    | None (Copied from `walk`)                                               |
| `burn`           | Burning animation  | `0`     | `10`          | `0.05`       | `1`    | None (Copied from `walk`)                                               |
| `fly_move`       | Flying movement    | `16`    | `8`           | `0.035`      | `1`    | None                                                                    |
| `fly_idle`       | Flying idle        | `16`    | `8`           | `0.035`      | `1`    | None                                                                    |
| `attack_dash`    | Dash attack        | `16`    | `8`           | `0.035`      | `1`    | `Event frame="0" name="dash"`                                           |
| `attack_ranged`  | Ranged attack      | `32`    | `4`           | `0.06`       | `0`    | `Event frame="1" name="attack_shoot"`                                   |

### Animation Events:

Some animations include `<Event>` tags, which trigger specific game actions at certain frames.

*   **`attack_dash`**: Triggers a "dash" event on frame 0.
*   **`attack_ranged`**: Triggers an "attack\_shoot" event on frame 1.

**Note:** Animations like `run`, `burn`, `fly_move`, and `fly_idle` appear to share sprite sheet coordinates and frame counts with other animations, suggesting they might be visually similar or derived from existing ones. Modifying these could involve adjusting `pos_x`, `pos_y`, or the frames themselves within the `firebug.png` file.