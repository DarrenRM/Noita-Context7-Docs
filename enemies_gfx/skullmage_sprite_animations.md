---
title: Skullmage Sprite Animations
category: data/enemies_gfx
---

# Skullmage Sprite Animations

This document details the sprite animations for the Skullmage enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The primary sprite for the Skullmage is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/skullmage.png` - The path to the sprite sheet.
*   **offset\_x**: `9` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `19` - Vertical offset for the sprite's origin.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation state.

### Animation States:

#### `stand`

*   **Description**: The idle animation for the Skullmage.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `0`
    *   `frame_count`: `8`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.09` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `1` (loops indefinitely)

#### `walk`

*   **Description**: The walking animation.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `24`
    *   `frame_count`: `8`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.07` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `1` (loops indefinitely)
*   **Events**:
    *   `step` event on frames 2 and 6, triggering a sound or action.

#### `run`

*   **Description**: The running animation. Note: This appears to be a copy of the `walk` animation's sprite data but with a faster `frame_wait`.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `24`
    *   `frame_count`: `8`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.06` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `1` (loops indefinitely)
*   **Events**:
    *   `step` event on frames 2 and 6.

#### `burn`

*   **Description**: The animation when the Skullmage is burning. Similar sprite data to `walk` and `run`.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `24`
    *   `frame_count`: `8`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.06` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `1` (loops indefinitely)
*   **Events**:
    *   `step` event on frames 2 and 6.

#### `attack_ranged`

*   **Description**: The animation for ranged attacks.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `72`
    *   `has_offset`: `1`
    *   `offset_x`: `10`
    *   `offset_y`: `19`
    *   `frame_count`: `6`
    *   `frame_width`: `20`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.09` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `0` (plays once)
*   **Events**:
    *   `shoot_magic` event on frame 3.

#### `attack`

*   **Description**: A general attack animation. Appears to use the same sprite data as `attack_ranged`.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `72`
    *   `has_offset`: `1`
    *   `offset_x`: `10`
    *   `offset_y`: `19`
    *   `frame_count`: `6`
    *   `frame_width`: `20`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.09` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `0` (plays once)
*   **Events**:
    *   `shoot_magic` event on frame 3.

#### `jump_up`

*   **Description**: The animation when initiating a jump.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `96`
    *   `frame_count`: `4`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.07` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `0` (plays once)
    *   `next_animation`: `jumping` (transitions to the `jumping` animation)
*   **Events**:
    *   `jump` event on frame 0.

#### `jumping`

*   **Description**: The animation while the Skullmage is in the air after jumping.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `96`
    *   `frame_count`: `4`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.06` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `1` (loops indefinitely while jumping)

#### `fly_idle`

*   **Description**: The idle animation when flying.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `48`
    *   `frame_count`: `4`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.09` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `1` (loops indefinitely)

#### `fly_move`

*   **Description**: The animation when moving while flying.
*   **Key Attributes**:
    *   `pos_x`: `0`
    *   `pos_y`: `48`
    *   `frame_count`: `4`
    *   `frame_width`: `18`
    *   `frame_height`: `24`
    *   `frame_wait`: `0.09` (seconds per frame)
    *   `frames_per_row`: `8`
    *   `loop`: `1` (loops indefinitely)