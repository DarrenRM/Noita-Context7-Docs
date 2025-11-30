---
title: Laser Projectile Graphics
category: projectiles_gfx
---

---

# Laser Projectile Graphics

This document describes the graphical assets for the "laser" projectile in Noita, as defined in `laser.xml`.

## Sprite Definition

The primary sprite definition for the laser projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/laser.png` - The texture file used for the sprite.
*   **offset\_x**: `3` - Horizontal offset for the sprite.
*   **offset\_y**: `1` - Vertical offset for the sprite.
*   **default\_animation**: `fireball` - The name of the default animation to play.

## Animations

Defines the animations used by the sprite.

### RectAnimation: `fireball`

This animation defines the visual frames for the laser projectile.

#### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the texture for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the texture for the animation frames.
*   **frame\_count**: `2` - The total number of frames in the animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `2` - The number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).