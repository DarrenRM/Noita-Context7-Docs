---
title: Spearbot Sprite Animations
category: entities
---

# Spearbot Sprite Animations

This document details the sprite animations for the Spearbot enemy in Noita, as defined in its XML configuration. It focuses on key attributes for AI-assisted modding, such as animation names, frame data, and event triggers.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the Spearbot.

### Key Attributes:

*   **filename**: `data/enemies_gfx/spearbot.png` - The path to the sprite sheet.
*   **offset\_x**: `18` - Horizontal offset of the sprite.
*   **offset\_y**: `31` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## RectAnimation Elements

Each `<RectAnimation>` tag defines a specific animation sequence.

### Animation Details:

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| **name**          | The identifier for the animation (e.g., "stand", "walk", "attack\_ranged"). |
| **frame\_count**  | The total number of frames in the animation.                             |
| **frame\_width**  | The width of each individual frame in pixels.                            |
| **frame\_height** | The height of each individual frame in pixels.                           |
| **frames\_per\_row** | How many frames are arranged horizontally on the sprite sheet.           |
| **frame\_wait**   | The duration (in seconds) each frame is displayed before advancing.      |
| **pos\_x**        | The horizontal starting position of the animation frames on the sprite sheet. |
| **pos\_y**        | The vertical starting position of the animation frames on the sprite sheet. |
| **loop**          | `0` indicates the animation does not loop, `1` (or omitted) indicates it does. |

### Notable Animations:

*   **stand**: The idle animation.
    *   `frame_count`: 8
    *   `frame_height`: 36
    *   `frame_wait`: 0.09
    *   `frame_width`: 36
    *   `frames_per_row`: 10
    *   `pos_y`: 0
*   **walk**: The walking animation.
    *   `frame_count`: 6
    *   `frame_height`: 36
    *   `frame_wait`: 0.09
    *   `frame_width`: 36
    *   `frames_per_row`: 10
    *   `pos_y`: 36
*   **run**: The running animation.
    *   `frame_count`: 6
    *   `frame_height`: 36
    *   `frame_wait`: 0.09
    *   `frame_width`: 36
    *   `frames_per_row`: 10
    *   `pos_y`: 36
*   **burn**: The burning animation.
    *   `frame_count`: 6
    *   `frame_height`: 36
    *   `frame_wait`: 0.09
    *   `frame_width`: 36
    *   `frames_per_row`: 10
    *   `pos_y`: 36
*   **attack\_ranged**: The ranged attack animation.
    *   `frame_count`: 10
    *   `frame_height`: 36
    *   `frame_wait`: 0.08
    *   `frame_width`: 36
    *   `frames_per_row`: 10
    *   `loop`: 0 (does not loop)
    *   `pos_y`: 144
*   **fly\_move**: The flying movement animation.
    *   `frame_count`: 6
    *   `frame_height`: 36
    *   `frame_wait`: 0.09
    *   `frame_width`: 36
    *   `frames_per_row`: 8
    *   `pos_y`: 108
*   **fly\_idle**: The flying idle animation.
    *   `frame_count`: 6
    *   `frame_height`: 36
    *   `frame_wait`: 0.09
    *   `frame_width`: 36
    *   `frames_per_row`: 8
    *   `pos_y`: 72

## Event Elements

Events are triggered at specific frames within an animation.

### Key Attributes:

*   **name**: The name of the event (e.g., "step", "shoot\_thunder"). This is crucial for scripting.
*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **probability**: The chance of the event occurring (usually 1 for guaranteed events).
*   **check\_physics\_material**: If `1`, the event might be influenced by the physics material of the ground.
*   **max\_distance**: Maximum distance for certain physics-related events.
*   **on\_finished**: `0` typically means the event does not stop the animation.

### Example Event (from `attack_ranged`):

*   **name**: `"shoot_thunder"`
*   **frame**: `5`
*   **check\_physics\_material**: `0`
*   **max\_distance**: `500`
*   **on\_finished**: `0`
*   **probability**: `1`

This event signifies the moment the Spearbot fires its ranged attack.