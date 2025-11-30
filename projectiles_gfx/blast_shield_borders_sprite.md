---
title: Blast Shield Borders Sprite
category: projectiles_gfx
---

# Blast Shield Borders Sprite

This document describes the sprite definition for the "blast shield borders" projectile graphics in Noita. It outlines the visual appearance and animation properties of this sprite.

## Sprite Definition

The main `<Sprite>` element defines the base properties of the graphic.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/blast_borders.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `32` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `32` - The vertical offset of the sprite's origin.
*   **`default_animation`**: `spawn` - The animation to play by default when the sprite is first loaded.
*   **`color_r`**: `0.7` - Red component of the sprite's tint.
*   **`color_g`**: `0.95` - Green component of the sprite's tint.
*   **`color_b`**: `1` - Blue component of the sprite's tint.

## Animations

The sprite utilizes two distinct animations: `spawn` and `fireball`.

### `spawn` Animation

This animation is the initial visual effect when the blast shield borders appear.

*   **`name`**: `spawn`
*   **`pos_x`**: `0` - The starting X coordinate within the sprite sheet for this animation.
*   **`pos_y`**: `0` - The starting Y coordinate within the sprite sheet for this animation.
*   **`frame_count`**: `5` - The total number of frames in this animation.
*   **`frame_width`**: `64` - The width of each individual frame.
*   **`frame_height`**: `64` - The height of each individual frame.
*   **`frame_wait`**: `0.02` - The time in seconds to wait between frames.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **`next_animation`**: `fireball` - The animation to transition to after this one completes.
*   **`loop`**: `0` - Indicates that this animation does not loop (it plays once).

### `fireball` Animation

This animation likely represents the ongoing visual effect of the blast shield borders.

*   **`name`**: `fireball`
*   **`pos_x`**: `0` - The starting X coordinate within the sprite sheet for this animation.
*   **`pos_y`**: `64` - The starting Y coordinate within the sprite sheet for this animation.
*   **`frame_count`**: `4` - The total number of frames in this animation.
*   **`frame_width`**: `64` - The width of each individual frame.
*   **`frame_height`**: `64` - The height of each individual frame.
*   **`frame_wait`**: `0.01` - The time in seconds to wait between frames.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1` - Indicates that this animation loops indefinitely.