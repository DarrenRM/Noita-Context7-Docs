---
title: Meatvine Part B (Vine_b_1) Sprite
category: entities
---

---

# Meatvine Part B (Vine_b_1) Sprite

This document describes the sprite data for a specific part of the "meatvine" entity in Noita, identified as `vine_b_1`.

## Sprite Definition

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/meatvine/vine_parts/vine_b.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is active.

## Animation: `stand`

The `stand` animation is a simple, static frame animation.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame in pixels.
*   **frame\_height**: `3` - The height of each individual frame in pixels.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).