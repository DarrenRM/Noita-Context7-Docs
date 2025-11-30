---
title: Boss Spirit Sprite Definitions
category: entities
---

# Boss Spirit Sprite Definitions

This document details the sprite definitions for the Boss Spirit entity in Noita, focusing on its visual animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and its positioning.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `filename`  | Path to the sprite image file.                  |
| `offset_x`  | Horizontal offset for the sprite.               |
| `offset_y`  | Vertical offset for the sprite.                 |
| `default_animation` | The animation to play by default. |

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the Boss Spirit. Each animation consists of a sequence of frames from the sprite sheet.

### Key Animation Attributes

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `name`           | The name of the animation (e.g., "stand", "walk", "fly_move").              |
| `pos_x`          | X-coordinate of the top-left corner of the animation frames on the sprite sheet. |
| `pos_y`          | Y-coordinate of the top-left corner of the animation frames on the sprite sheet. |
| `frame_count`    | The total number of frames in this animation.                               |
| `frame_width`    | The width of each individual frame.                                         |
| `frame_height`   | The height of each individual frame.                                        |
| `frame_wait`     | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row` | How many frames are arranged horizontally on the sprite sheet.              |
| `loop`           | Whether the animation should loop (`1` for yes, `0` for no).                |

### Animation Types and Events

The Boss Spirit has several distinct animations, each with specific frame layouts and potential events.

#### Stand Animation

*   **Name:** `stand`
*   **Description:** The default idle animation.
*   **Sprite Sheet Position:** `pos_x="0"`, `pos_y="0"`
*   **Frame Count:** `1`
*   **Frame Size:** `32x32`
*   **Frame Wait:** `0.2`
*   **Loop:** `1`

#### Walk Animation

*   **Name:** `walk`
*   **Description:** Animation for when the spirit is walking.
*   **Sprite Sheet Position:** `pos_x="0"`, `pos_y="32"`
*   **Frame Count:** `6`
*   **Frame Size:** `32x32`
*   **Frame Wait:** `0.1`
*   **Loop:** `1`
*   **Events:**
    *   `frame="0"`: `step` (probability `1`, `check_physics_material="1"`)
    *   `frame="3"`: `step` (probability `1`, `check_physics_material="1"`)

#### Look Around Animation

*   **Name:** `look_around`
*   **Description:** Animation for the spirit looking around.
*   **Sprite Sheet Position:** `pos_x="0"`, `pos_y="64"`
*   **Frame Count:** `10`
*   **Frame Size:** `32x32`
*   **Frame Wait:** `0.15`
*   **Loop:** `0` (Does not loop)

#### Swim Animations

There are two distinct swim animations, `swim_idle` and `swim_move`, which share the same sprite sheet position but may have different timing or events.

*   **Names:** `swim_idle`, `swim_move`
*   **Description:** Animations for swimming.
*   **Sprite Sheet Position:** `pos_x="0"`, `pos_y="96"`
*   **Frame Count:** `6`
*   **Frame Size:** `32x32`
*   **Frame Wait:** `0.13`
*   **Loop:** `1`
*   **Events (for both):**
    *   `frame="2"`: `paddle` (probability `1`, `check_physics_material="0"`)
    *   `frame="5"`: `paddle` (probability `1`, `check_physics_material="0"`)

#### Flight Animations

Similar to swimming, there are `fly_idle` and `fly_move` animations.

*   **Names:** `fly_move`, `fly_idle`
*   **Description:** Animations for flying.
*   **Sprite Sheet Position:** `pos_x="0"`, `pos_y="128"`
*   **Frame Count:** `4`
*   **Frame Size:** `32x32`
*   **Frame Wait:** `0.09` (for `fly_move`), `0.12` (for `fly_idle`)
*   **Loop:** `1`