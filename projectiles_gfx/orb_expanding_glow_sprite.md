---
title: Orb Expanding Glow Sprite
category: projectiles_gfx
---

# Orb Expanding Glow Sprite

This documentation describes the sprite definition for the "orb_expanding_glow" projectile in Noita. It focuses on the visual aspects and animation of this projectile.

## Sprite Definition

The main sprite is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/orb_expanding_glow.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `15` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `15` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"fireball"` - The name of the animation that plays by default.

## Animation Definition

The animation for this sprite is defined using the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `"fireball"` - The identifier for this animation.
*   **pos\_x**: `"0"` - The starting X position of the animation frames within the texture.
*   **pos\_y**: `"0"` - The starting Y position of the animation frames within the texture.
*   **frame\_count**: `12` - The total number of frames in the animation.
*   **frame\_width**: `30` - The width of each individual animation frame.
*   **frame\_height**: `30` - The height of each individual animation frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `12` - The number of frames arranged horizontally in the texture.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).