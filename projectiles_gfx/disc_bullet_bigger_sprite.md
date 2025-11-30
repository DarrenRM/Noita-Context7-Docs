---
title: Disc Bullet Bigger Sprite
category: projectiles_gfx
---

# Disc Bullet Bigger Sprite

This documentation describes the sprite definition for the "disc_bullet_bigger" projectile in Noita. It outlines the visual assets and animations used for this projectile.

## Sprite Definition

The main `Sprite` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/disc_bullet_bigger.png` - The path to the sprite sheet containing the projectile's graphics.
*   **offset_x**: `12.5` - The horizontal offset of the sprite's origin.
*   **offset_y**: `12.5` - The vertical offset of the sprite's origin.
*   **default_animation**: `"fireball"` - The animation to play by default when the projectile is active.

## Animations

The `Sprite` element contains one or more `RectAnimation` elements, defining different animation sequences.

### Animation: `fireball`

This animation is likely used when the projectile is in motion.

#### Key Attributes:

*   **name**: `"fireball"` - The identifier for this animation.
*   **pos_x**: `"0"` - The starting X position within the sprite sheet for this animation.
*   **pos_y**: `"0"` - The starting Y position within the sprite sheet for this animation.
*   **frame_count**: `"3"` - The total number of frames in this animation.
*   **frame_width**: `"25"` - The width of each individual frame.
*   **frame_height**: `"25"` - The height of each individual frame.
*   **frame_wait**: `"0.02"` - The time in seconds to wait between frames.
*   **frames_per_row**: `"3"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that this animation should loop continuously.

### Animation: `on_ground`

This animation is likely used when the projectile has landed or is at rest.

#### Key Attributes:

*   **name**: `"on_ground"` - The identifier for this animation.
*   **pos_x**: `"0"` - The starting X position within the sprite sheet for this animation.
*   **pos_y**: `"0"` - The starting Y position within the sprite sheet for this animation.
*   **frame_count**: `"1"` - The total number of frames in this animation.
*   **frame_width**: `"25"` - The width of each individual frame.
*   **frame_height**: `"25"` - The height of each individual frame.
*   **frame_wait**: `"0.02"` - The time in seconds to wait between frames.
*   **frames_per_row**: `"3"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"0"` - Indicates that this animation should not loop (play only once).