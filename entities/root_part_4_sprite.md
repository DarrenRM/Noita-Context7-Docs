---
title: Root Part 4 Sprite
category: entities
---

# Root Part 4 Sprite

This document describes the sprite and animation data for a specific part of the "root" entity in Noita.

## Sprite

The primary sprite for this root part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/root/root_parts/root.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is active.

## Animation

The entity utilizes a single animation named "stand".

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `24` - The starting X coordinate within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y coordinate within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `6` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.