---
title: Miniblob Sprite Definitions
category: enemies_gfx
---

# Miniblob Sprite Definitions

This document details the sprite definitions for the Miniblob enemy in Noita, focusing on its visual animations and associated events.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and default animation for the Miniblob.

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `filename`    | `data/enemies_gfx/miniblob.png`     | Path to the sprite sheet containing all animation frames.                   |
| `offset_x`    | `7`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | `13`                                | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `stand`                             | The animation to play by default when the enemy is idle.                    |

## Animations

The Miniblob has several distinct animations, each defined by a `<RectAnimation>` tag.

### `stand` Animation

This animation represents the Miniblob in its idle state.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `name`           | `stand` | The name of this animation.                                                 |
| `frame_count`    | `6`     | Total number of frames in this animation.                                   |
| `frame_width`    | `14`    | Width of each individual frame in pixels.                                   |
| `frame_height`   | `16`    | Height of each individual frame in pixels.                                  |
| `frames_per_row` | `8`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`     | `0.16`  | Time in seconds to wait between each frame.                                 |
| `pos_x`          | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`          | `1`     | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### `attack` Animation

This animation is triggered when the Miniblob performs an attack.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `name`           | `attack`| The name of this animation.                                                 |
| `frame_count`    | `3`     | Total number of frames in this animation.                                   |
| `frame_width`    | `14`    | Width of each individual frame in pixels.                                   |
| `frame_height`   | `16`    | Height of each individual frame in pixels.                                  |
| `frames_per_row` | `8`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`     | `0.064` | Time in seconds to wait between each frame.                                 |
| `loop`           | `0`     | `0` indicates this animation does not loop.                                 |
| `pos_x`          | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`          | `1`     | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

#### Events within `attack`

*   **`bite` Event**:
    *   `frame`: `0`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `0`
    *   `on_finished`: `0`

### `walk` Animation

This animation represents the Miniblob's walking movement.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `name`           | `walk`  | The name of this animation.                                                 |
| `frame_count`    | `5`     | Total number of frames in this animation.                                   |
| `frame_width`    | `15`    | Width of each individual frame in pixels.                                   |
| `frame_height`   | `17`    | Height of each individual frame in pixels.                                  |
| `frames_per_row` | `8`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`     | `0.1`   | Time in seconds to wait between each frame.                                 |
| `pos_x`          | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`          | `18`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | Indicates frames are shrunk by one pixel.                                   |

#### Events within `walk`

*   **`step` Event (Frame 2)**:
    *   `frame`: `2`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `1`
    *   `on_finished`: `0`
*   **`step` Event (Frame 4)**:
    *   `frame`: `4`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `1`
    *   `on_finished`: `0`

### `run` Animation

This animation is used when the Miniblob is running.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `name`           | `run`   | The name of this animation.                                                 |
| `frame_count`    | `5`     | Total number of frames in this animation.                                   |
| `frame_width`    | `15`    | Width of each individual frame in pixels.                                   |
| `frame_height`   | `17`    | Height of each individual frame in pixels.                                  |
| `frames_per_row` | `8`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`     | `0.1`   | Time in seconds to wait between each frame.                                 |
| `pos_x`          | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`          | `18`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | Indicates frames are shrunk by one pixel.                                   |

#### Events within `run`

*   **`step` Event (Frame 2)**:
    *   `frame`: `2`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `1`
    *   `on_finished`: `0`
*   **`step` Event (Frame 4)**:
    *   `frame`: `4`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `1`
    *   `on_finished`: `0`

### `burn` Animation

This animation plays when the Miniblob is on fire.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `name`           | `burn`  | The name of this animation.                                                 |
| `frame_count`    | `5`     | Total number of frames in this animation.                                   |
| `frame_width`    | `15`    | Width of each individual frame in pixels.                                   |
| `frame_height`   | `17`    | Height of each individual frame in pixels.                                  |
| `frames_per_row` | `8`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`     | `0.1`   | Time in seconds to wait between each frame.                                 |
| `pos_x`          | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`          | `18`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | Indicates frames are shrunk by one pixel.                                   |

#### Events within `burn`

*   **`step` Event (Frame 2)**:
    *   `frame`: `2`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `1`
    *   `on_finished`: `0`
*   **`step` Event (Frame 4)**:
    *   `frame`: `4`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `1`
    *   `on_finished`: `0`

### `jump_up` Animation

This animation plays when the Miniblob jumps upwards.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `name`           | `jump_up`| The name of this animation.                                                 |
| `frame_count`    | `1`     | Total number of frames in this animation.                                   |
| `frame_width`    | `15`    | Width of each individual frame in pixels.                                   |
| `frame_height`   | `17`    | Height of each individual frame in pixels.                                  |
| `frames_per_row` | `8`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`     | `0.082` | Time in seconds to wait between each frame.                                 |
| `loop`           | `0`     | `0` indicates this animation does not loop.                                 |
| `pos_x`          | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`          | `18`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | Indicates frames are shrunk by one pixel.                                   |

#### Events within `jump_up`

*   **`jump` Event**:
    *   `frame`: `0`
    *   `probability`: `1`
    *   `max_distance`: `500`
    *   `check_physics_material`: `1`
    *   `on_finished`: `0`

### `jump_fall` Animation

This animation plays when the Miniblob is falling after a jump.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `name`           | `jump_fall`| The name of this animation.                                                 |
| `frame_count`    | `1`     | Total number of frames in this animation.                                   |
| `frame_width`    | `15`    | Width of each individual frame in pixels.                                   |
| `frame_height`   | `17`    | Height of each individual frame in pixels.                                  |
| `frames_per_row` | `8`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`     | `0.082` | Time in seconds to wait between each frame.                                 |
| `loop`           | `0`     | `0` indicates this animation does not loop.                                 |
| `pos_x`          | `30`    | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`          | `18`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | Indicates frames are shrunk by one pixel.                                   |