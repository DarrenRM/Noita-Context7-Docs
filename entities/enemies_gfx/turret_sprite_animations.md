---
title: Turret Sprite Animations
category: entities/enemies_gfx
---

# Turret Sprite Animations

This document details the sprite animations for the "turret" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/turret.png` - Path to the sprite sheet.
*   **`offset_x`**: `12` - Horizontal offset for the sprite.
*   **`offset_y`**: `15` - Vertical offset for the sprite.
*   **`default_animation`**: `"stand"` - The animation to play by default.

## Animations

### `stand` Animation

This animation defines the turret's idle state.

#### Key Attributes:

*   **`name`**: `"stand"`
*   **`frame_count`**: `1` - Number of frames in this animation.
*   **`frame_width`**: `24` - Width of each frame.
*   **`frame_height`**: `18` - Height of each frame.
*   **`frames_per_row`**: `6` - Frames are arranged in 6 columns.
*   **`frame_wait`**: `0.16` - Delay between frames in seconds.
*   **`pos_x`**: `0` - Starting X position of the animation frames on the sprite sheet.
*   **`pos_y`**: `1` - Starting Y position of the animation frames on the sprite sheet.

### `attack_ranged` Animation

This animation defines the turret's ranged attack sequence.

#### Key Attributes:

*   **`name`**: `"attack_ranged"`
*   **`frame_count`**: `6` - Number of frames in this animation.
*   **`frame_width`**: `25` - Width of each frame.
*   **`frame_height`**: `19` - Height of each frame.
*   **`frames_per_row`**: `6` - Frames are arranged in 6 columns.
*   **`frame_wait`**: `0.07` - Delay between frames in seconds.
*   **`loop`**: `0` - This animation does not loop.
*   **`pos_x`**: `0` - Starting X position of the animation frames on the sprite sheet.
*   **`pos_y`**: `20` - Starting Y position of the animation frames on the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates a slight shrinking effect on frames.

#### Events within `attack_ranged`:

*   **`shoot_sniper` Event**:
    *   **`frame`**: `3` - The event triggers on the 3rd frame of the animation.
    *   **`name`**: `"shoot_sniper"` - The name of the event, likely linked to a game action.
    *   **`probability`**: `1` - The event is guaranteed to trigger when its frame is reached.
    *   **`max_distance`**: `500` - The maximum distance at which this event can occur.
    *   **`check_physics_material`**: `0` - Physics material is not checked for this event.
    *   **`on_finished`**: `0` - The event does not trigger upon animation completion.