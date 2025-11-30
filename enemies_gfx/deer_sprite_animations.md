---
title: Deer Sprite Animations
category: enemies_gfx
---

# Deer Sprite Animations

This document details the sprite animations for the Deer entity in Noita, as defined in `data/enemies_gfx/deer.xml`. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/deer.png` - The path to the sprite sheet.
*   **offset\_x**: `16` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `17` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation played by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "eat").
*   **pos\_x**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.

### Animation Breakdown:

| Animation Name | `pos_y` | `frame_count` | `frame_wait` | `loop` | Key Events                                                              | Description                               |
| :------------- | :------ | :------------ | :----------- | :----- | :---------------------------------------------------------------------- | :---------------------------------------- |
| `stand`        | `0`     | `1`           | `0.2`        | `1`    | None                                                                    | Idle standing animation.                  |
| `walk`         | `32`    | `6`           | `0.1`        | `1`    | `step` (frames 0, 3)                                                    | Walking animation.                        |
| `run`          | `32`    | `6`           | `0.1`        | `1`    | `step` (frames 0, 3)                                                    | Placeholder for running animation.        |
| `lower_head`   | `64`    | `5`           | `0.2`        | `0`    | None                                                                    | Animation for lowering the deer's head.   |
| `eat`          | `96`    | `12`          | `0.3`        | `1`    | `eat` (frames 3, 9)                                                     | Animation for eating.                     |
| `raise_head`   | `128`   | `4`           | `0.2`        | `0`    | None                                                                    | Animation for raising the deer's head.    |
| `wag_tail`     | `160`   | `5`           | `0.09`       | `1`    | None                                                                    | Animation for wagging its tail.           |
| `poop`         | `160`   | `5`           | `0.09`       | `1`    | None                                                                    | Animation for defecating.                 |
| `look_around`  | `192`   | `10`          | `0.15`       | `0`    | None                                                                    | Animation for looking around.             |
| `party`        | `224`   | `6`           | `0.09`       | `1`    | None                                                                    | Festive animation.                        |
| `lie_down`     | `256`   | `6`           | `0.12`       | `0`    | None                                                                    | Animation for lying down.                 |
| `sleep`        | `288`   | `2`           | `1.3`        | `1`    | None                                                                    | Sleeping animation.                       |
| `rise_up`      | `320`   | `6`           | `0.12`       | `0`    | None                                                                    | Animation for rising up.                  |
| `attack`       | `64`    | `5`           | `0.2`        | `0`    | None                                                                    | Placeholder for attack animation.         |
| `swim_idle`    | `352`   | `6`           | `0.13`       | `1`    | `paddle` (frames 0, 3)                                                   | Idle swimming animation.                  |
| `swim_move`    | `352`   | `6`           | `0.11`       | `1`    | `paddle` (frames 0, 3)                                                   | Moving while swimming animation.          |

### Animation Events:

Some animations include `<Event>` tags, which trigger specific game events at certain frames.

*   **frame**: The frame number at which the event occurs.
*   **name**: The name of the event (e.g., "step", "eat", "paddle").
*   **probability**: The chance of the event occurring (usually `1` for guaranteed).
*   **check\_physics\_material**: If `1`, the event checks the physics material of the ground; otherwise, it does not.

This structured data allows AI to understand the visual components and behaviors of the Deer entity for modding purposes.