---
title: Scavenger Grenade Projectile Graphics
category: projectiles_gfx
---

# Scavenger Grenade Projectile Graphics

This document details the graphical assets for the Scavenger Grenade projectile in Noita, as defined in `grenade_scavenger.xml`.

## Sprite Definition

The primary sprite for the Scavenger Grenade is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/grenade_scavenger.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `4` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `4` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the default animation to play.

## Animation: `fireball`

The `fireball` animation defines how the sprite is rendered over time, creating a visual effect.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `8` - The height of each individual animation frame.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).