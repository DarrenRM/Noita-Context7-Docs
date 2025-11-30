---
title: Alternative Fireball Sprite Animations
category: projectiles_gfx
---

# Alternative Fireball Sprite Animations

This document details the sprite animations for an alternative fireball projectile in Noita, as defined in `fireball_alt.xml`. It focuses on the visual aspects and animation properties.

## Sprite Definition

The main `<Sprite>` element defines the base image and its offsets.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `"spawn"`
*   **`filename`**: The path to the sprite sheet image.
    *   Value: `"data/projectiles_gfx/fireball_alt.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"16"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"12"`

## RectAnimation Elements

Two `<RectAnimation>` elements define distinct animation sequences: `fireball` and `spawn`.

### 1. `fireball` Animation

This animation represents the main visual of the fireball in motion.

#### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   Value: `"fireball"`
*   **`frame_count`**: Total number of frames in the animation.
    *   Value: `"4"`
*   **`frame_width`**: Width of each individual frame.
    *   Value: `"33"`
*   **`frame_height`**: Height of each individual frame.
    *   Value: `"25"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"4"`
*   **`frame_wait`**: Duration each frame is displayed before advancing.
    *   Value: `"0.035"`
*   **`pos_x`**: X-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: Indicates if frames should be shrunk by one pixel.
    *   Value: `"1"` (True)

### 2. `spawn` Animation

This animation likely represents the initial appearance or spawning effect of the fireball.

#### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   Value: `"spawn"`
*   **`frame_count`**: Total number of frames in the animation.
    *   Value: `"4"`
*   **`frame_width`**: Width of each individual frame.
    *   Value: `"32"`
*   **`frame_height`**: Height of each individual frame.
    *   Value: `"24"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"4"`
*   **`frame_wait`**: Duration each frame is displayed before advancing.
    *   Value: `"0.08"`
*   **`loop`**: Whether the animation should loop.
    *   Value: `"0"` (False - plays once)
*   **`next_animation`**: The animation to transition to after this one finishes.
    *   Value: `"fireball"`
*   **`pos_x`**: X-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   Value: `"26"`