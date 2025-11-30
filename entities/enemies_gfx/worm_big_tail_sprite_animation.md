---
title: Worm Big Tail Sprite Animation
category: entities/enemies_gfx
---

# Worm Big Tail Sprite Animation

This document details the sprite and animation data for the "worm_big_tail" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the worm's big tail segment is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/worm_big_tail.png` - Specifies the image file containing the sprite frames.
*   **`offset_x`**: `14` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `12` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `stand` - The animation that plays by default when the sprite is active.

## Animations

The worm's tail segment utilizes two distinct animations: "stand" and "eat". Both are defined using the `<RectAnimation>` tag, indicating they are derived from a rectangular grid of frames within the sprite sheet.

### Animation: `stand`

This animation likely represents the idle or resting state of the worm's tail.

#### Key Attributes:

*   **`name`**: `stand` - The identifier for this animation.
*   **`pos_x`**: `0` - Starting X position within the sprite sheet for this animation.
*   **`pos_y`**: `0` - Starting Y position within the sprite sheet for this animation.
*   **`frame_count`**: `4` - The total number of frames in this animation.
*   **`frame_width`**: `28` - The width of each individual frame in pixels.
*   **`frame_height`**: `25` - The height of each individual frame in pixels.
*   **`frame_wait`**: `0.082` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **`loop`**: `1` - Indicates that the animation will loop continuously.

### Animation: `eat`

This animation likely represents the worm's tail segment performing an eating action.

#### Key Attributes:

*   **`name`**: `eat` - The identifier for this animation.
*   **`pos_x`**: `0` - Starting X position within the sprite sheet for this animation.
*   **`pos_y`**: `0` - Starting Y position within the sprite sheet for this animation.
*   **`frame_count`**: `4` - The total number of frames in this animation.
*   **`frame_width`**: `28` - The width of each individual frame in pixels.
*   **`frame_height`**: `25` - The height of each individual frame in pixels.
*   **`frame_wait`**: `0.082` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **`loop`**: `1` - Indicates that the animation will loop continuously.