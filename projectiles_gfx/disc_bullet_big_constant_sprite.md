---
title: Disc Bullet Big Constant Sprite
category: projectiles_gfx
---

# Disc Bullet Big Constant Sprite

This documentation describes the sprite definition for a "Disc Bullet Big" projectile in Noita, focusing on its visual properties and animations.

## Sprite Definition

The core sprite is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the sprite.
    *   `data/projectiles_gfx/disc_bullet_big.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `8.5`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `8.5`
*   **`default_animation`**: The animation to play by default.
    *   `fireball`

## Animations

The projectile utilizes two distinct animations: `fireball` for active flight and `on_ground` for when it lands.

### `fireball` Animation

This animation defines the visual sequence for the projectile while it's in motion.

#### Key Attributes:

*   **`name`**: `fireball`
*   **`pos_x`**: Starting X position within the texture.
    *   `0`
*   **`pos_y`**: Starting Y position within the texture.
    *   `0`
*   **`frame_count`**: Total number of frames in the animation.
    *   `4`
*   **`frame_width`**: Width of each individual frame.
    *   `17`
*   **`frame_height`**: Height of each individual frame.
    *   `17`
*   **`frame_wait`**: Time in seconds between frames.
    *   `0.04`
*   **`frames_per_row`**: Number of frames in a single row of the texture.
    *   `4`
*   **`loop`**: Whether the animation should loop.
    *   `1` (True)

### `on_ground` Animation

This animation defines the visual for the projectile when it has landed.

#### Key Attributes:

*   **`name`**: `on_ground`
*   **`pos_x`**: Starting X position within the texture.
    *   `0`
*   **`pos_y`**: Starting Y position within the texture.
    *   `0`
*   **`frame_count`**: Total number of frames in the animation.
    *   `1`
*   **`frame_width`**: Width of each individual frame.
    *   `17`
*   **`frame_height`**: Height of each individual frame.
    *   `17`
*   **`frame_wait`**: Time in seconds between frames.
    *   `0.02`
*   **`frames_per_row`**: Number of frames in a single row of the texture.
    *   `4`
*   **`loop`**: Whether the animation should loop.
    *   `0` (False)