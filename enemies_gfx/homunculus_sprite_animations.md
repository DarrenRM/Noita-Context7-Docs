---
title: Homunculus Sprite Animations
category: data/enemies_gfx
---

# Homunculus Sprite Animations

This document details the sprite animations for the Homunculus enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/homunculus.png` - Path to the sprite sheet.
*   **`default_animation`**: `"stand"` - The animation played when the entity is idle.
*   **`offset_x`**: `6.5` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `10` - Vertical offset for the sprite's origin.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### `stand` Animation:

*   **`name`**: `"stand"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.1` - Duration each frame is displayed.
*   **`pos_y`**: `1` - Vertical position of the animation frames within the sprite sheet.

### `walk` Animation:

*   **`name`**: `"walk"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_y`**: `18`
*   **Events**:
    *   **`step`**: Triggered at frame `0` and `3`.

### `run` Animation:

*   **`name`**: `"run"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_y`**: `18`
*   **Events**:
    *   **`step`**: Triggered at frame `0` and `3`.

### `burn` Animation:

*   **`name`**: `"burn"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_y`**: `18`
*   **Events**:
    *   **`step`**: Triggered at frame `0` and `3`.

### `fly_idle` Animation:

*   **`name`**: `"fly_idle"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `17`
*   **`frame_height`**: `18`
*   **`frames_per_row`**: `15`
*   **`frame_wait`**: `0.12`
*   **`pos_y`**: `35`
*   **`shrink_by_one_pixel`**: `1` - Indicates a slight shrinking effect.

### `fly_move` Animation:

*   **`name`**: `"fly_move"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `17`
*   **`frame_height`**: `18`
*   **`frames_per_row`**: `15`
*   **`frame_wait`**: `0.12`
*   **`pos_y`**: `35`
*   **`shrink_by_one_pixel`**: `1`

### `attack_ranged` Animation:

*   **`name`**: `"attack_ranged"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `17`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.04`
*   **`pos_y`**: `53`
*   **`loop`**: `0` - This animation does not loop.
*   **Events**:
    *   **`shoot_magic`**: Triggered at frame `3`.

### `attack` Animation:

*   **`name`**: `"attack"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `17`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.04`
*   **`pos_y`**: `53`
*   **`loop`**: `0` - This animation does not loop.
*   **Events**:
    *   **`shoot_melee`**: Triggered at frame `3`.

## Animation Events

Events within animations can trigger specific game actions.

### Key Event Attributes:

*   **`name`**: The type of event (e.g., `step`, `shoot_magic`).
*   **`frame`**: The specific frame number within the animation when the event occurs.
*   **`check_physics_material`**: `1` or `0`. If `1`, the event might depend on the material the entity is standing on.
*   **`max_distance`**: `500` - Maximum distance for certain event checks.
*   **`probability`**: `1` - The likelihood of the event triggering (1 means always).
*   **`on_finished`**: `0` - Indicates if the event should only trigger when the animation finishes.