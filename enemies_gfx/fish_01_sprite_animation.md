---
title: Fish 01 Sprite Animation
category: data/enemies_gfx
---

# Fish 01 Sprite Animation

This document details the sprite animations for the `fish_01` enemy in Noita. It focuses on the key attributes defining its visual behavior.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/fish_01.png` - The path to the sprite sheet.
*   **`offset_x`**: `5` - Horizontal offset for the sprite.
*   **`offset_y`**: `5` - Vertical offset for the sprite.
*   **`default_animation`**: `stand` - The animation to play by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation state.

### Animation Details:

Each `<RectAnimation>` defines a sequence of frames from the sprite sheet.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| **`name`**      | The identifier for the animation (e.g., `stand`, `walk`, `death`).       |
| **`pos_x`**     | Starting X-coordinate on the sprite sheet for this animation.            |
| **`pos_y`**     | Starting Y-coordinate on the sprite sheet for this animation.            |
| **`frame_count`** | The total number of frames in this animation.                            |
| **`frame_width`** | The width of each individual frame in pixels.                            |
| **`frame_height`**| The height of each individual frame in pixels.                           |
| **`frame_wait`**| The duration (in seconds) each frame is displayed before advancing.      |
| **`frames_per_row`**| The number of frames that fit horizontally on the sprite sheet.        |
| **`loop`**      | `1` for looping animations, `0` for non-looping (plays once).            |

### Specific Animations:

*   **`stand`**:
    *   `frame_count`: 2
    *   `frame_width`: 10
    *   `frame_height`: 10
    *   `frame_wait`: 0.15
    *   `frames_per_row`: 10
    *   `loop`: 1

*   **`walk`**:
    *   `frame_count`: 2
    *   `frame_width`: 10
    *   `frame_height`: 10
    *   `frame_wait`: 0.2
    *   `frames_per_row`: 10
    *   `loop`: 1

*   **`jump_up`**:
    *   `frame_count`: 2
    *   `frame_width`: 10
    *   `frame_height`: 10
    *   `frame_wait`: 0.3
    *   `frames_per_row`: 10
    *   `loop`: 1

*   **`jump_falling`**:
    *   `frame_count`: 2
    *   `frame_width`: 10
    *   `frame_height`: 10
    *   `frame_wait`: 0.4
    *   `frames_per_row`: 10
    *   `loop`: 1

*   **`death`**:
    *   `frame_count`: 1
    *   `frame_width`: 10
    *   `frame_height`: 10
    *   `frame_wait`: 0.2
    *   `frames_per_row`: 10
    *   `loop`: 0