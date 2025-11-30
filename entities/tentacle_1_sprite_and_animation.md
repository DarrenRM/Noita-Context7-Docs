---
title: Tentacle 1 Sprite and Animation
category: entities
---

# Tentacle 1 Sprite and Animation

This document describes the sprite and animation data for the "tentacle_1" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/parallel/tentacles/tentacle.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is spawned.

## Animation: `stand`

The `stand` animation is a simple, non-looping animation.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the sprite frame's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the sprite frame's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `11` - The height of each individual frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false). In this case, it does not loop.