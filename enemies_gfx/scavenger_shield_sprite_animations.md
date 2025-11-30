---
title: Scavenger Shield Sprite Animations
category: enemies_gfx
---

# Scavenger Shield Sprite Animations

This document details the sprite animations for the "Scavenger Shield" enemy in Noita, as defined in its XML configuration file. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base properties for the enemy's visual representation.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `"stand"`
*   **`filename`**: The path to the sprite sheet image.
    *   Value: `"data/enemies_gfx/scavenger_shield.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"7"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"15"`

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### `stand` Animation

*   **`name`**: `"stand"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.2` (seconds per frame)
*   **`pos_x`**: `0` (X-coordinate of the animation block on the sprite sheet)
*   **`pos_y`**: `1` (Y-coordinate of the animation block on the sprite sheet)

### `walk` Animation

*   **`name`**: `"walk"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.082` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `23`
*   **Events**: This animation includes two `"step"` events.
    *   **`frame`**: `2` and `5`
    *   **`check_physics_material`**: `1` (checks the material of the ground)
    *   **`name`**: `"step"`

### `run` Animation

*   **`name`**: `"run"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.082` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `23`
*   **Events**: Similar to `walk`, includes two `"step"` events.

### `burn` Animation

*   **`name`**: `"burn"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.06` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `23`
*   **Events**: Includes two `"step"` events.

### `jump_up` Animation

*   **`name`**: `"jump_up"`
*   **`frame_count`**: `3`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.082` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `45`
*   **`loop`**: `0` (does not loop)
*   **Events**: Includes one `"jump"` event.
    *   **`frame`**: `0`
    *   **`name`**: `"jump"`

### `jump_fall` Animation

*   **`name`**: `"jump_fall"`
*   **`frame_count`**: `2`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.082` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `67`
*   **`loop`**: `0` (does not loop)

### `attack_ranged` Animation

*   **`name`**: `"attack_ranged"`
*   **`frame_count`**: `3`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.07` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `89`
*   **`loop`**: `0` (does not loop)
*   **Events**: Includes one `"shoot_heal"` event.
    *   **`frame`**: `1`
    *   **`name`**: `"shoot_heal"`
    *   **`check_physics_material`**: `0` (does not check physics material)

### `fly_idle` Animation

*   **`name`**: `"fly_idle"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `21`
*   **`frame_height`**: `22`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.12` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `111`
*   **`shrink_by_one_pixel`**: `1`

### `fly_move` Animation

*   **`name`**: `"fly_move"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `20`
*   **`frame_height`**: `21`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.09` (seconds per frame)
*   **`pos_x`**: `0`
*   **`pos_y`**: `133`