---
title: Tiny Orb Projectile Sprite
category: data/projectiles_gfx/
---

# Tiny Orb Projectile Sprite

This document describes the sprite definition for the "orb_tiny" projectile in Noita, focusing on its visual representation and animation.

## Sprite Definition

The core sprite is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/orb_tiny.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `3` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `3` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to be played by default.

## Animation Definition

The projectile utilizes a rectangular animation for its visual effect.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X-coordinate within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y-coordinate within the sprite sheet for the animation frames.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `6` - The width of each individual animation frame.
*   **frame\_height**: `6` - The height of each individual animation frame.
*   **frame\_wait**: `0.07` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).