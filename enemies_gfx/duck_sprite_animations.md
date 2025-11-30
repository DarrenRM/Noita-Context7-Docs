---
title: Duck Sprite Animations
category: data/enemies_gfx/
---

# Duck Sprite Animations

This document details the sprite animations for the "duck" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base properties for the duck's visual representation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/duck.png` - The path to the sprite sheet image.
*   **`offset_x`**: `6` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `9` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `stand` - The animation to play by default.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### `stand` Animation

*   **`name`**: `stand`
*   **`frame_count`**: `5`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.12` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0` - Starting X coordinate on the sprite sheet.
*   **`pos_y`**: `1` - Starting Y coordinate on the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates a slight shrinking effect.

### `walk` Animation

*   **`name`**: `walk`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.09` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `14`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `walk`:

*   **`step`**: Triggered at frames `1` and `4`. `check_physics_material="1"` suggests it might play a sound or trigger an effect related to the ground surface.

### `run` Animation

*   **`name`**: `run`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.08` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `27`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `run`:

*   **`step`**: Triggered at frames `1` and `4`, similar to the `walk` animation.

### `burn` Animation

*   **`name`**: `burn`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.08` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `27` (Note: Shares `pos_y` with `run`, implying it might be on the same row of the sprite sheet, but with different frames used).
*   **`shrink_by_one_pixel`**: `1`

#### Events within `burn`:

*   **`step`**: Triggered at frames `1` and `4`.

### `swim_idle` Animation

*   **`name`**: `swim_idle`
*   **`frame_count`**: `4`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.25` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `40`

### `swim_move` Animation

*   **`name`**: `swim_move`
*   **`frame_count`**: `4`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.25` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `40` (Note: Shares `pos_y` with `swim_idle`).

### `jump_up` Animation

*   **`name`**: `jump_up`
*   **`frame_count`**: `2`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.06` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `53`

### `jump_fall` Animation

*   **`name`**: `jump_fall`
*   **`frame_count`**: `2`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.06` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `53` (Note: Shares `pos_y` with `jump_up`).

#### Events within `jump_fall`:

*   **`flap`**: Triggered at frame `0` with a `probability="0.7"`. `check_physics_material="0"` suggests this event is not tied to the ground.

### `attack_dash` Animation

*   **`name`**: `attack_dash`
*   **`frame_count`**: `2`
*   **`frame_width`**: `13`
*   **`frame_height`**: `13`
*   **`frame_wait`**: `0.06` seconds per frame.
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `53` (Note: Shares `pos_y` with `jump_up` and `jump_fall`).