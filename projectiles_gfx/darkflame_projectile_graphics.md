---
title: Darkflame Projectile Graphics
category: projectiles_gfx
---

---

# Darkflame Projectile Graphics

This document details the graphical assets for the "darkflame" projectile in Noita, as defined in `darkflame.xml`. It focuses on the sprite definition and its associated animations.

## Sprite Definition

The main sprite for the darkflame projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/darkflame.png` - Specifies the image file containing the sprite frames.
*   **`default_animation`**: `spawn` - Sets the initial animation to play when the projectile is created.
*   **`offset_x`**: `6` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `6` - Vertical offset for the sprite's origin.

## Animations

The projectile utilizes two distinct animations: `spawn` and `fireball`.

### `spawn` Animation

This animation plays when the projectile is first created, likely a visual effect for its appearance.

#### Key Attributes:

*   **`name`**: `spawn`
*   **`frame_count`**: `6` - The total number of frames in this animation.
*   **`frame_width`**: `12` - The width of each individual frame.
*   **`frame_height`**: `12` - The height of each individual frame.
*   **`frames_per_row`**: `6` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **`loop`**: `0` - This animation does not loop.
*   **`next_animation`**: `fireball` - After completing, it transitions to the `fireball` animation.
*   **`pos_x`**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **`pos_y`**: `14` - Y-coordinate of the animation's top-left corner within the sprite sheet.

### `fireball` Animation

This animation represents the main visual of the projectile in flight.

#### Key Attributes:

*   **`name`**: `fireball`
*   **`frame_count`**: `6` - The total number of frames in this animation.
*   **`frame_width`**: `13` - The width of each individual frame.
*   **`frame_height`**: `13` - The height of each individual frame.
*   **`frames_per_row`**: `6` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **`pos_x`**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **`pos_y`**: `1` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates that each frame might be slightly smaller than the defined `frame_width`/`frame_height` by one pixel, potentially for scaling effects.