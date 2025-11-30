---
title: Pebble Sprite Animations
category: entities
---

# Pebble Sprite Animations

This document details the sprite animations for the "Pebble" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its default animation.

```xml
<Sprite
 filename="data/enemies_gfx/pebble.png"
 offset_x="8"
 offset_y="13" 
 default_animation="stand">
```

*   **`filename`**: Specifies the path to the sprite sheet.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its entity.
*   **`default_animation`**: Sets the animation to play when no other animation is specified.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Animation Attributes

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `name`           | The identifier for the animation (e.g., "stand", "walk", "burn").           |
| `pos_x`, `pos_y` | The starting coordinates of the animation frames on the sprite sheet.       |
| `frame_count`    | The total number of frames in the animation.                                |
| `frame_width`    | The width of each individual frame.                                         |
| `frame_height`   | The height of each individual frame.                                        |
| `frame_wait`     | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row` | The number of frames that fit horizontally on a single row of the sprite sheet. |
| `loop`           | Whether the animation should repeat (`1` for true, `0` for false).          |

### Animation Types

#### `stand`

*   **Description**: The default idle animation.
*   **Frames**: 4 frames.
*   **Frame Size**: 16x16 pixels.
*   **Frame Wait**: 0.2 seconds.
*   **Looping**: Yes.

#### `walk`

*   **Description**: Animation for when the pebble is walking.
*   **Frames**: 4 frames.
*   **Frame Size**: 16x16 pixels.
*   **Frame Wait**: 0.08 seconds.
*   **Looping**: Yes.

#### `run`

*   **Description**: Animation for when the pebble is running. Copied from `walk`.
*   **Frames**: 4 frames.
*   **Frame Size**: 16x16 pixels.
*   **Frame Wait**: 0.09 seconds.
*   **Looping**: Yes.

#### `burn`

*   **Description**: Animation for when the pebble is burning. Copied from `walk`.
*   **Frames**: 4 frames.
*   **Frame Size**: 16x16 pixels.
*   **Frame Wait**: 0.09 seconds.
*   **Looping**: Yes.

#### `jump_up`

*   **Description**: Animation played when the pebble jumps upwards.
*   **Frames**: 1 frame.
*   **Frame Size**: 16x16 pixels.
*   **Frame Wait**: 0.09 seconds.
*   **Looping**: Yes.
*   **Events**:
    *   `frame="0"`: Triggers a `jump` event.
        *   `probability="1"`: Always triggers.
        *   `check_physics_material="1"`: Requires a physics material to be present.

#### `fall_down`

*   **Description**: Animation played when the pebble is falling.
*   **Frames**: 1 frame.
*   **Frame Size**: 16x16 pixels.
*   **Frame Wait**: 0.09 seconds.
*   **Looping**: Yes.
*   **Sprite Sheet Offset**: Starts at `pos_x="16"` on the sprite sheet, indicating it uses a different frame than the initial animations.