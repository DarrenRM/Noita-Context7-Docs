---
title: Tiny Fungus B Sprite Animation
category: entities
---

# Tiny Fungus B Sprite Animation

This document details the sprite animations for the "fungus_tiny_b" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/fungus_tiny_b.png` - The path to the sprite sheet.
*   **`default_animation`**: `"stand"` - The animation played by default.
*   **`offset_x`**: `"5"` - Horizontal offset for the sprite.
*   **`offset_y`**: `"10"` - Vertical offset for the sprite.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### `stand` Animation

*   **`name`**: `"stand"`
*   **`frame_count`**: `12`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.12` - Duration each frame is displayed.
*   **`pos_x`**: `0` - X-coordinate of the animation's top-left corner on the sprite sheet.
*   **`pos_y`**: `1` - Y-coordinate of the animation's top-left corner on the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates if frames are shrunk by one pixel.

### `walk` Animation

*   **`name`**: `"walk"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.2`
*   **`pos_x`**: `0`
*   **`pos_y`**: `15`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `walk`:

*   **`step`**: Triggered at frame `2` and `5`.
    *   `check_physics_material`: `1` - Checks the physics material of the ground.
    *   `max_distance`: `500` - Maximum distance for the check.
    *   `probability`: `1` - Always triggers if conditions are met.

### `run` Animation

*   **`name`**: `"run"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.2`
*   **`pos_x`**: `0`
*   **`pos_y`**: `15`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `run`:

*   **`step`**: Triggered at frame `2` and `5`.
    *   `check_physics_material`: `1`
    *   `max_distance`: `500`
    *   `probability`: `1`

### `burn` Animation

*   **`name`**: `"burn"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.2`
*   **`pos_x`**: `0`
*   **`pos_y`**: `15`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `burn`:

*   **`step`**: Triggered at frame `2` and `5`.
    *   `check_physics_material`: `1`
    *   `max_distance`: `500`
    *   `probability`: `1`

### `jump_up` Animation

*   **`name`**: `"jump_up"`
*   **`frame_count`**: `1`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `1`
*   **`frame_wait`**: `0.2`
*   **`pos_x`**: `0`
*   **`pos_y`**: `29`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `jump_up`:

*   **`jump`**: Triggered at frame `0`.
    *   `check_physics_material`: `1`
    *   `max_distance`: `500`
    *   `probability`: `1`

### `jump_fall` Animation

*   **`name`**: `"jump_fall"`
*   **`frame_count`**: `1`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `1`
*   **`frame_wait`**: `0.2`
*   **`pos_x`**: `0`
*   **`pos_y`**: `43`
*   **`shrink_by_one_pixel`**: `1`