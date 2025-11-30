---
title: Scavenger Small Grenade Sprite
category: projectiles_gfx
---

# Scavenger Small Grenade Sprite

This document describes the sprite data for the "scavenger_small" grenade projectile in Noita.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/projectiles_gfx/grenade_scavenger_small.png` - Specifies the image file used for the sprite.
*   **offset_x**: `4` - Horizontal offset for the sprite's origin.
*   **offset_y**: `4` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - The name of the default animation to play.

## Animation: `fireball`

The projectile uses a `RectAnimation` for its visual effect.

### Key Attributes

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `8` - The width of each individual frame.
*   **frame_height**: `8` - The height of each individual frame.
*   **frame_wait**: `0.04` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).