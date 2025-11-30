---
title: Homunculus Fire Sprite Animations
category: data/enemies_gfx
---

# Homunculus Fire Sprite Animations

This document details the sprite animations for the Homunculus Fire enemy in Noita, as defined in its XML configuration file. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/homunculus_fire.png` - The path to the sprite sheet.
*   **`default_animation`**: `stand` - The animation to play by default.
*   **`offset_x`**: `6.5` - Horizontal offset for the sprite.
*   **`offset_y`**: `10` - Vertical offset for the sprite.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### `stand` Animation

*   **`name`**: `stand`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.1` - Duration each frame is displayed.
*   **`pos_x`**: `0` - X-coordinate of the animation's top-left corner on the sprite sheet.
*   **`pos_y`**: `1` - Y-coordinate of the animation's top-left corner on the sprite sheet.

### `walk` Animation

*   **`name`**: `walk`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_x`**: `0`
*   **`pos_y`**: `18`
*   **Events**:
    *   **`step`**: Triggered at frame `0` and `3`. `check_physics_material="1"` suggests it reacts to the ground.

### `run` Animation

*   **`name`**: `run`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_x`**: `0`
*   **`pos_y`**: `18`
*   **Events**:
    *   **`step`**: Triggered at frame `0` and `3`. `check_physics_material="1"` suggests it reacts to the ground.

### `burn` Animation

*   **`name`**: `burn`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `16`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_x`**: `0`
*   **`pos_y`**: `18`
*   **Events**:
    *   **`step`**: Triggered at frame `0` and `3`. `check_physics_material="1"` suggests it reacts to the ground.

### `fly_idle` Animation

*   **`name`**: `fly_idle`
*   **`frame_count`**: `4`
*   **`frame_width`**: `17`
*   **`frame_height`**: `18`
*   **`frames_per_row`**: `15`
*   **`frame_wait`**: `0.12`
*   **`pos_x`**: `0`
*   **`pos_y`**: `35`
*   **`shrink_by_one_pixel`**: `1` - Indicates a slight scaling or cropping.

### `fly_move` Animation

*   **`name`**: `fly_move`
*   **`frame_count`**: `4`
*   **`frame_width`**: `17`
*   **`frame_height`**: `18`
*   **`frames_per_row`**: `15`
*   **`frame_wait`**: `0.12`
*   **`pos_x`**: `0`
*   **`pos_y`**: `35`
*   **`shrink_by_one_pixel`**: `1`

### `attack_ranged` Animation

*   **`name`**: `attack_ranged`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `17`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.04`
*   **`loop`**: `0` - This animation does not loop.
*   **`pos_x`**: `0`
*   **`pos_y`**: `53`
*   **Events**:
    *   **`shoot_magic`**: Triggered at frame `3`. `check_physics_material="0"` means it doesn't depend on the ground material.

### `attack` Animation

*   **`name`**: `attack`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `17`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.04`
*   **`loop`**: `0` - This animation does not loop.
*   **`pos_x`**: `0`
*   **`pos_y`**: `53`
*   **Events**:
    *   **`shoot_melee`**: Triggered at frame `3`. `check_physics_material="0"` means it doesn't depend on the ground material.