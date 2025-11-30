---
title: Tiny Fungus Sprite Animations
category: data/enemies_gfx
---

# Tiny Fungus Sprite Animations

This document details the sprite animations for the "fungus_tiny" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the overall sprite properties and the default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/fungus_tiny.png` - The image file containing all animation frames.
*   **`default_animation`**: `"stand"` - The animation played by default when the sprite is active.
*   **`offset_x`**: `5` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `10` - Vertical offset for the sprite's origin.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### `stand` Animation

*   **`name`**: `"stand"`
*   **`frame_count`**: `12`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.12` seconds per frame.
*   **`pos_y`**: `1` - Vertical position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates frames are shrunk by one pixel.

### `walk` Animation

*   **`name`**: `"walk"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.2` seconds per frame.
*   **`pos_y`**: `15` - Vertical position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1`

#### Events within `walk`:

*   **`step`**: Triggered at frames `2` and `5`. These events likely correspond to footstep sounds or particle effects.
    *   `check_physics_material="1"`: Checks the physics material of the ground.
    *   `max_distance="500"`: Maximum distance for the check.
    *   `probability="1"`: Always triggers.

### `run` Animation

*   **`name`**: `"run"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.2` seconds per frame.
*   **`pos_y`**: `15`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `run`:

*   **`step`**: Triggered at frames `2` and `5`. Similar to the `walk` animation's step events.

### `burn` Animation

*   **`name`**: `"burn"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.2` seconds per frame.
*   **`pos_y`**: `15`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `burn`:

*   **`step`**: Triggered at frames `2` and `5`. These might represent burning effects or damage indicators.

### `jump_up` Animation

*   **`name`**: `"jump_up"`
*   **`frame_count`**: `1`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `1`
*   **`frame_wait`**: `0.2` seconds per frame.
*   **`pos_y`**: `29`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `jump_up`:

*   **`jump`**: Triggered at frame `0`. This event likely signifies the start of a jump.

### `jump_fall` Animation

*   **`name`**: `"jump_fall"`
*   **`frame_count`**: `1`
*   **`frame_width`**: `13`
*   **`frame_height`**: `14`
*   **`frames_per_row`**: `1`
*   **`frame_wait`**: `0.2` seconds per frame.
*   **`pos_y`**: `43`
*   **`shrink_by_one_pixel`**: `1`

This animation likely represents the sprite during its falling phase after a jump. It has no defined events in this snippet.