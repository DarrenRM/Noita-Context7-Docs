---
title: Player Mine Emissive Sprite
category: projectiles_gfx
---

# Player Mine Emissive Sprite

This document describes the sprite data for the player's mine projectile, specifically its emissive texture. This file defines the visual appearance and animations for the mine.

## Sprite Definition

The main `<Sprite>` element defines the base properties of the projectile's visual representation.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/mine_player_emissive.png`
    *   Specifies the texture file used for this sprite.
*   **`offset_x`**: `12`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `18`
    *   Vertical offset for the sprite's origin.

## Animations

The `<Sprite>` element contains one or more `<RectAnimation>` elements, each defining a specific animation sequence.

### `stand` Animation

This animation likely represents the default, idle state of the mine.

#### Key Attributes:

*   **`name`**: `stand`
*   **`frame_count`**: `1`
    *   Indicates a single frame for this animation.
*   **`frame_height`**: `25`
    *   Height of each animation frame in pixels.
*   **`frame_wait`**: `0.16`
    *   Time in seconds to wait between frames.
*   **`frame_width`**: `25`
    *   Width of each animation frame in pixels.
*   **`frames_per_row`**: `8`
    *   Number of frames arranged horizontally in the texture.
*   **`pos_x`**: `0`
    *   Starting X-coordinate of the animation frames within the texture.
*   **`pos_y`**: `1`
    *   Starting Y-coordinate of the animation frames within the texture.
*   **`shrink_by_one_pixel`**: `1`
    *   Indicates if frames should be shrunk by one pixel.

### `detonate` Animation

This animation defines the visual sequence for the mine's detonation.

#### Key Attributes:

*   **`name`**: `detonate`
*   **`frame_count`**: `8`
    *   The number of frames in the detonation sequence.
*   **`frame_height`**: `25`
    *   Height of each animation frame in pixels.
*   **`frame_wait`**: `0.09`
    *   Shorter wait time for a more rapid detonation effect.
*   **`frame_width`**: `25`
    *   Width of each animation frame in pixels.
*   **`frames_per_row`**: `8`
    *   Number of frames arranged horizontally in the texture.
*   **`pos_x`**: `0`
    *   Starting X-coordinate of the animation frames within the texture.
*   **`pos_y`**: `1`
    *   Starting Y-coordinate of the animation frames within the texture.
*   **`shrink_by_one_pixel`**: `1`
    *   Indicates if frames should be shrunk by one pixel.