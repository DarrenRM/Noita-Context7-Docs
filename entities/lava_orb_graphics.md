---
title: Lava Orb Graphics
category: entities
---

# Lava Orb Graphics

This document describes the graphical assets for the Lava Orb entity in Noita.

## Sprite

The main sprite definition for the Lava Orb.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/orb_mat_lava.png` - The texture file used for the sprite.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `fireball` - The animation to play by default.

## Animations

The Lava Orb has two distinct animations: `fireball` and `detonate`.

### `fireball` Animation

This animation represents the orb in its active, projectile state.

#### Key Attributes:

*   **name**: `fireball`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in the animation.
*   **frame\_width**: `20` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.05` - Time in seconds between frames.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true, 0 for false).

### `detonate` Animation

This animation plays when the orb detonates.

#### Key Attributes:

*   **name**: `detonate`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `20` - Starting Y position within the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in the animation.
*   **frame\_width**: `20` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.03` - Time in seconds between frames.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation loops.