---
title: Monk Hand Sprite Animations
category: entities/enemies_gfx
---

# Monk Hand Sprite Animations

This document details the sprite animations for the Monk Hand enemy in Noita, focusing on its visual representation and animation properties.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/monk_hand.png` - The path to the sprite sheet containing all animation frames.
*   **`offset_x`**: `6` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `14` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `open` - The animation that plays by default when the sprite is loaded.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation sequence.

### `open` Animation

This animation likely represents the Monk Hand opening or preparing an action.

#### Key Attributes:

*   **`name`**: `open` - The identifier for this animation.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `0` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **`frame_count`**: `4` - The total number of frames in this animation.
*   **`frame_width`**: `14` - The width of each individual animation frame.
*   **`frame_height`**: `18` - The height of each individual animation frame.
*   **`frame_wait`**: `0.1` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **`loop`**: `0` - Indicates that this animation does not loop (plays once).

### `close` Animation

This animation likely represents the Monk Hand closing or completing an action.

#### Key Attributes:

*   **`name`**: `close` - The identifier for this animation.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `18` - The starting Y coordinate of the animation frames within the sprite sheet. This value indicates the frames for `close` are located below the `open` frames in the sprite sheet.
*   **`frame_count`**: `4` - The total number of frames in this animation.
*   **`frame_width`**: `14` - The width of each individual animation frame.
*   **`frame_height`**: `18` - The height of each individual animation frame.
*   **`frame_wait`**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next. Slightly slower than the `open` animation.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **`loop`**: `0` - Indicates that this animation does not loop (plays once).