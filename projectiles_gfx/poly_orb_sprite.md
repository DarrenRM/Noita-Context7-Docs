---
title: Poly Orb Sprite
category: projectiles_gfx
---

---

# Poly Orb Sprite

This document describes the sprite and animation data for the "polyorb" projectile in Noita.

## Sprite Definition

The primary sprite for the polyorb is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/polyorb.png` - The image file containing the sprite frames.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `6` - Vertical offset for the sprite's origin.
*   **default\_animation**: `stand` - The animation to play by default.

## Animation: "stand"

The "stand" animation defines how the polyorb sprite is rendered over time.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual frame in pixels.
*   **frame\_height**: `12` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.082` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).