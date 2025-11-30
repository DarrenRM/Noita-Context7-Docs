---
title: Meatvine Part A Sprite
category: entities
---

# Meatvine Part A Sprite

This document describes the sprite data for a part of the "meatvine" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/meatvine/vine_parts/vine_a.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

The sprite utilizes a single animation named "stand".

### RectAnimation: "stand"

This animation defines how the sprite is rendered.

#### Key Attributes:

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `24` - The X-coordinate of the top-left corner of the sprite frame within the texture.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the sprite frame within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of a single animation frame.
*   **frame\_height**: `3` - The height of a single animation frame.
*   **frame\_wait**: `1` - The duration (in frames) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).