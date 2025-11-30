---
title: Boss Centipede Blood Orb Graphics
category: entities
---

# Boss Centipede Blood Orb Graphics

This document details the graphical components for the Boss Centipede's blood orb entity in Noita.

## Sprite

The main sprite definition for the blood orb.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/orb_mat_blood.png` - The texture file used for the sprite.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `"fireball"` - The animation to play by default.

## Animations

The entity utilizes two distinct animations: `fireball` and `detonate`.

### `fireball` Animation

This animation likely represents the orb's projectile state.

#### Key Attributes:

*   **name**: `"fireball"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"8"` - Total number of frames in the animation.
*   **frame\_width**: `"20"` - Width of each individual frame.
*   **frame\_height**: `"20"` - Height of each individual frame.
*   **frame\_wait**: `"0.05"` - Time in seconds between frames.
*   **frames\_per\_row**: `"8"` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates the animation loops (1 for true).

### `detonate` Animation

This animation is likely used when the orb explodes or detonates.

#### Key Attributes:

*   **name**: `"detonate"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"20"` - Starting Y position within the sprite sheet. (Note: This is offset from the `fireball` animation's Y position, suggesting a different row in the sprite sheet).
*   **frame\_count**: `"8"` - Total number of frames in the animation.
*   **frame\_width**: `"20"` - Width of each individual frame.
*   **frame\_height**: `"20"` - Height of each individual frame.
*   **frame\_wait**: `"0.03"` - Time in seconds between frames (faster than `fireball`).
*   **frames\_per\_row**: `"8"` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates the animation loops (1 for true).