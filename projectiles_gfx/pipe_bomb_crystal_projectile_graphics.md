---
title: Pipe Bomb Crystal Projectile Graphics
category: projectiles_gfx
---

# Pipe Bomb Crystal Projectile Graphics

This document details the graphical assets for the "pipe_bomb_crystal" projectile in Noita, focusing on its sprite and animation definitions.

## Sprite Definition

The main sprite for the projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default.
    *   Value: `"fireball"`
*   **`filename`**: The path to the image file containing the sprite frames.
    *   Value: `"data/projectiles_gfx/pipe_bomb_crystal.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"4.5"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"4.5"`

## Animation Definitions

The projectile utilizes two distinct animations: `fireball` and `on_ground`.

### 1. `fireball` Animation

This animation likely represents the projectile in motion.

#### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   Value: `"fireball"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"4"`
*   **`frame_width`**: The width of each individual frame.
    *   Value: `"10"`
*   **`frame_height`**: The height of each individual frame.
    *   Value: `"10"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"4"`
*   **`frame_wait`**: The duration (in frames or seconds, depending on context) each frame is displayed before advancing.
    *   Value: `"1000"` (Likely milliseconds, indicating a slower animation)
*   **`pos_x`**: X-coordinate of the animation's starting position within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: Y-coordinate of the animation's starting position within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.
    *   Value: `"1"`

### 2. `on_ground` Animation

This animation is likely for when the projectile has landed or is stationary.

#### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   Value: `"on_ground"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"1"` (A single frame animation)
*   **`frame_width`**: The width of each individual frame.
    *   Value: `"10"`
*   **`frame_height`**: The height of each individual frame.
    *   Value: `"10"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"4"`
*   **`frame_wait`**: The duration each frame is displayed.
    *   Value: `"0.02"` (Likely seconds, indicating a very fast or static display)
*   **`loop`**: Whether the animation should loop.
    *   Value: `"0"` (Does not loop)
*   **`pos_x`**: X-coordinate of the animation's starting position within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: Y-coordinate of the animation's starting position within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.
    *   Value: `"1"`