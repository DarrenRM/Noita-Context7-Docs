---
title: Homunculus Laser Sprite Animations
category: enemies_gfx
---

# Homunculus Laser Sprite Animations

This document details the sprite animations for the Homunculus Laser enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`default_animation`**: "stand" - The animation played when the enemy is idle.
*   **`filename`**: "data/enemies_gfx/homunculus_laser.png" - The path to the sprite sheet.
*   **`offset_x`**: "6.5" - Horizontal offset for sprite positioning.
*   **`offset_y`**: "10" - Vertical offset for sprite positioning.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### `stand` Animation

*   **`name`**: "stand"
*   **`frame_count`**: 6
*   **`frame_width`**: 16
*   **`frame_height`**: 16
*   **`frames_per_row`**: 6
*   **`frame_wait`**: 0.1

### `walk` Animation

*   **`name`**: "walk"
*   **`frame_count`**: 6
*   **`frame_width`**: 16
*   **`frame_height`**: 16
*   **`frames_per_row`**: 6
*   **`frame_wait`**: 0.085
*   **Events**:
    *   `step` at frame 0
    *   `step` at frame 3

### `run` Animation

*   **`name`**: "run"
*   **`frame_count`**: 6
*   **`frame_width`**: 16
*   **`frame_height`**: 16
*   **`frames_per_row`**: 6
*   **`frame_wait`**: 0.085
*   **Events**:
    *   `step` at frame 0
    *   `step` at frame 3

### `burn` Animation

*   **`name`**: "burn"
*   **`frame_count`**: 6
*   **`frame_width`**: 16
*   **`frame_height`**: 16
*   **`frames_per_row`**: 6
*   **`frame_wait`**: 0.085
*   **Events**:
    *   `step` at frame 0
    *   `step` at frame 3

### `fly_idle` Animation

*   **`name`**: "fly_idle"
*   **`frame_count`**: 4
*   **`frame_width`**: 17
*   **`frame_height`**: 18
*   **`frames_per_row`**: 15
*   **`frame_wait`**: 0.12
*   **`shrink_by_one_pixel`**: 1

### `fly_move` Animation

*   **`name`**: "fly_move"
*   **`frame_count`**: 4
*   **`frame_width`**: 17
*   **`frame_height`**: 18
*   **`frames_per_row`**: 15
*   **`frame_wait`**: 0.12
*   **`shrink_by_one_pixel`**: 1

### `attack_ranged` Animation

*   **`name`**: "attack_ranged"
*   **`frame_count`**: 6
*   **`frame_width`**: 16
*   **`frame_height`**: 17
*   **`frames_per_row`**: 6
*   **`frame_wait`**: 0.04
*   **`loop`**: 0 (Does not loop)
*   **Events**:
    *   `shoot_magic` at frame 3

### `attack` Animation

*   **`name`**: "attack"
*   **`frame_count`**: 6
*   **`frame_width`**: 16
*   **`frame_height`**: 17
*   **`frames_per_row`**: 6
*   **`frame_wait`**: 0.04
*   **`loop`**: 0 (Does not loop)
*   **Events**:
    *   `shoot_melee` at frame 3

## Event Details

Events within animations trigger specific actions.

### `step` Event

*   **`check_physics_material`**: 1 (Checks for physics material)
*   **`max_distance`**: 500
*   **`on_finished`**: 0

### `shoot_magic` Event

*   **`check_physics_material`**: 0 (Does not check physics material)
*   **`max_distance`**: 500
*   **`on_finished`**: 0

### `shoot_melee` Event

*   **`check_physics_material`**: 0 (Does not check physics material)
*   **`max_distance`**: 500
*   **`on_finished`**: 0