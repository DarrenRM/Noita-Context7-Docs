---
title: Gazer Enemy Sprite Definitions
category: enemies_gfx
---

# Gazer Enemy Sprite Definitions

This document details the sprite and animation definitions for the "Gazer" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary `Sprite` tag defines the base image and its default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/gazer.png` - The path to the sprite sheet image.
*   **`default_animation`**: `stand` - The animation to play by default when the sprite is loaded.
*   **`offset_x`**: `16` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `22` - Vertical offset for the sprite's origin.

## Animation Definitions

The `Sprite` tag contains multiple `RectAnimation` tags, each defining a specific animation sequence.

### `stand` Animation

*   **`name`**: `stand`
*   **`frame_count`**: `4`
*   **`frame_width`**: `32`
*   **`frame_height`**: `32`
*   **`frames_per_row`**: `4`
*   **`frame_wait`**: `0.16` seconds per frame.
*   **`pos_x`**: `0`
*   **`pos_y`**: `1`

### `fly` Animation

*   **`name`**: `fly`
*   **`frame_count`**: `4`
*   **`frame_width`**: `32`
*   **`frame_height`**: `32`
*   **`frames_per_row`**: `4`
*   **`frame_wait`**: `0.16` seconds per frame.
*   **`pos_x`**: `0`
*   **`pos_y`**: `1`

### `fly_idle` Animation

*   **`name`**: `fly_idle`
*   **`frame_count`**: `4`
*   **`frame_width`**: `32`
*   **`frame_height`**: `32`
*   **`frames_per_row`**: `4`
*   **`frame_wait`**: `0.16` seconds per frame.
*   **`pos_x`**: `0`
*   **`pos_y`**: `1`

### `attack_ranged` Animation

*   **`name`**: `attack_ranged`
*   **`frame_count`**: `5`
*   **`frame_width`**: `33`
*   **`frame_height`**: `33`
*   **`frames_per_row`**: `5`
*   **`frame_wait`**: `0.1` seconds per frame.
*   **`loop`**: `0` (This animation does not loop).
*   **`pos_x`**: `0`
*   **`pos_y`**: `34`
*   **`shrink_by_one_pixel`**: `1` (Applies a 1-pixel shrink effect).

#### Events for `attack_ranged`:

*   **`shoot_fire`**:
    *   Triggered on `frame="1"`.
    *   `probability="1"` (Always triggers if frame is met).
    *   `max_distance="500"` (Effect is relevant up to this distance).
    *   `check_physics_material="0"` (Does not check physics material).
    *   `on_finished="0"` (Does not trigger on animation finish).
*   **`attack_shoot`**:
    *   Triggered on `frame="1"`.
    *   `probability="1"` (Always triggers if frame is met).
    *   `max_distance="500"` (Effect is relevant up to this distance).
    *   `check_physics_material="0"` (Does not check physics material).
    *   `on_finished="0"` (Does not trigger on animation finish).