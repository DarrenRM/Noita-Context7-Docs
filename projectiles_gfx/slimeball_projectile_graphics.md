---
title: Slimeball Projectile Graphics
category: projectiles_gfx
---

---

# Slimeball Projectile Graphics

This document details the graphical assets for the "slimeball" projectile in Noita, focusing on its sprite and animations.

## Sprite Definition

The core sprite for the slimeball is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/slimeball.png` - Specifies the image file containing the projectile's graphics.
*   **`offset_x`**: `12` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `12` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `spawn` - The animation to play by default when the projectile is created.

## Animations

The slimeball projectile utilizes two distinct animations: `fireball` and `spawn`.

### `fireball` Animation

This animation likely represents the projectile in its active, in-flight state.

#### Key Attributes:

*   **`name`**: `fireball`
*   **`pos_x`**: `0` - Starting X position within the sprite sheet.
*   **`pos_y`**: `0` - Starting Y position within the sprite sheet.
*   **`frame_count`**: `4` - Total number of frames in this animation.
*   **`frame_width`**: `24` - Width of each individual frame.
*   **`frame_height`**: `24` - Height of each individual frame.
*   **`frame_wait`**: `0.10` - Delay in seconds between frames.
*   **`frames_per_row`**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1` - Indicates that this animation should loop indefinitely.

### `spawn` Animation

This animation is likely used for the initial appearance or creation of the slimeball.

#### Key Attributes:

*   **`name`**: `spawn`
*   **`pos_x`**: `0` - Starting X position within the sprite sheet.
*   **`pos_y`**: `24` - Starting Y position within the sprite sheet. This indicates it's on a different row than the `fireball` animation.
*   **`frame_count`**: `4` - Total number of frames in this animation.
*   **`frame_width`**: `24` - Width of each individual frame.
*   **`frame_height`**: `24` - Height of each individual frame.
*   **`frame_wait`**: `0.02` - Delay in seconds between frames. This is a much faster animation than `fireball`.
*   **`frames_per_row`**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **`next_animation`**: `fireball` - Specifies that after this animation completes, the `fireball` animation should play.
*   **`loop`**: `0` - Indicates that this animation should not loop and will play only once.