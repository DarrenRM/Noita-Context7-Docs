---
title: Red Slimeball Projectile Graphics
category: projectiles_gfx
---

---

# Red Slimeball Projectile Graphics

This document details the graphical assets for the red slimeball projectile in Noita, as defined in `slimeball_red.xml`.

## Sprite Definition

The primary sprite definition for the red slimeball.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/slimeball_red.png` - The texture file containing the projectile's frames.
*   **offset\_x**: `12` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.
*   **default\_animation**: `spawn` - The animation to play when the projectile is first created.

## Animations

The projectile utilizes two distinct animations: `spawn` and `fireball`.

### `fireball` Animation

This animation likely represents the projectile in its active, moving state.

#### Key Attributes:

*   **name**: `fireball`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `4` - Total number of frames in this animation.
*   **frame\_width**: `24` - Width of each individual frame.
*   **frame\_height**: `24` - Height of each individual frame.
*   **frame\_wait**: `0.10` - Duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation will loop indefinitely.

### `spawn` Animation

This animation is played initially, likely depicting the projectile's emergence.

#### Key Attributes:

*   **name**: `spawn`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `24` - Starting Y position within the sprite sheet for this animation. This suggests the `spawn` frames are located below the `fireball` frames in the texture.
*   **frame\_count**: `4` - Total number of frames in this animation.
*   **frame\_width**: `24` - Width of each individual frame.
*   **frame\_height**: `24` - Height of each individual frame.
*   **frame\_wait**: `0.02` - Duration (in seconds) each frame is displayed. This is a much faster animation than `fireball`.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **next\_animation**: `fireball` - Specifies that the `fireball` animation will play immediately after `spawn` completes.
*   **loop**: `0` - Indicates the animation will play only once.