---
title: Boss Centipede Oil Orb Graphics
category: entities
---

# Boss Centipede Oil Orb Graphics

This document details the graphical assets for the Boss Centipede's oil orb projectile in Noita.

## Sprite Definition

The primary sprite definition for the oil orb.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/orb_mat_oil.png` - The texture file used for the sprite.
*   **offset\_x**: `10` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `10` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The animation to play by default.

## Animations

The oil orb utilizes two distinct animations: `fireball` and `detonate`.

### `fireball` Animation

This animation represents the orb in its active, projectile state.

#### Key Attributes:

*   **name**: `fireball`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in this animation.
*   **frame\_width**: `20` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.05` - Time in seconds between frames.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true).

### `detonate` Animation

This animation plays when the oil orb detonates.

#### Key Attributes:

*   **name**: `detonate`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `20` - Starting Y position within the sprite sheet. This indicates it's on the row below the `fireball` animation.
*   **frame\_count**: `8` - Total number of frames in this animation.
*   **frame\_width**: `20` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.03` - Time in seconds between frames. This animation is faster than `fireball`.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true).