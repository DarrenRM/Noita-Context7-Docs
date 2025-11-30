---
title: Ice Projectile Graphics
category: projectiles_gfx
---

---

# Ice Projectile Graphics

This document details the graphical assets for the "ice" projectile in Noita, as defined in `ice.xml`.

## Sprite Definition

The primary sprite definition for the ice projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/ice.png` - The texture file used for the projectile's visuals.
*   **offset\_x**: `7` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `spawn` - The animation to play by default when the projectile is created.

## Animations

The projectile utilizes two distinct animations: `spawn` and `fireball`.

### `spawn` Animation

This animation plays when the projectile is initially created.

#### Key Attributes:

*   **name**: `spawn`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `12` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `6` - The total number of frames in this animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.10` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **next\_animation**: `fireball` - The animation to transition to after this one completes.
*   **loop**: `0` - Indicates that this animation does not loop (plays once).

### `fireball` Animation

This animation plays after the `spawn` animation, likely representing the projectile in its active state.

#### Key Attributes:

*   **name**: `fireball`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `6` - The total number of frames in this animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that this animation loops continuously.