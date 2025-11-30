---
title: Bouncy Orb Projectile Graphics
category: projectiles_gfx
---

---

# Bouncy Orb Projectile Graphics

This document details the graphical assets for the "bouncy_orb" projectile in Noita, focusing on its sprite and animations.

## Sprite Definition

The main sprite for the bouncy orb is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/bouncy_orb.png` - Specifies the image file containing the projectile's graphics.
*   **`offset_x`**: `4.5` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `4.5` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `fireball` - The animation to play by default when the projectile is active.

## Animations

The bouncy orb utilizes two distinct animations: `fireball` and `on_ground`.

### `fireball` Animation

This animation likely represents the projectile in motion.

#### Key Attributes:

*   **`name`**: `fireball`
*   **`pos_x`**: `0` - Starting X position within the sprite sheet.
*   **`pos_y`**: `0` - Starting Y position within the sprite sheet.
*   **`frame_count`**: `4` - Total number of frames in this animation.
*   **`frame_width`**: `9` - Width of each individual frame.
*   **`frame_height`**: `9` - Height of each individual frame.
*   **`frame_wait`**: `1000` - Delay between frames in milliseconds (1 second).
*   **`frames_per_row`**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1` - Indicates that this animation should loop indefinitely.

### `on_ground` Animation

This animation is likely used when the projectile has landed or is stationary.

#### Key Attributes:

*   **`name`**: `on_ground`
*   **`pos_x`**: `0` - Starting X position within the sprite sheet.
*   **`pos_y`**: `0` - Starting Y position within the sprite sheet.
*   **`frame_count`**: `1` - Total number of frames in this animation.
*   **`frame_width`**: `9` - Width of each individual frame.
*   **`frame_height`**: `9` - Height of each individual frame.
*   **`frame_wait`**: `0.02` - Delay between frames in milliseconds (20 milliseconds).
*   **`frames_per_row`**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates that this animation should play only once.