---
title: Boss Centipede Long Limb A Sprite
category: entities
---

# Boss Centipede Long Limb A Sprite

This document describes the sprite and animation data for a limb of the Boss Centipede enemy in Noita.

## Sprite

The primary sprite for this limb is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/limbs/limb_long_A.png` - The image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `8` - Vertical offset of the sprite.

## RectAnimation

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `stand` - The name of this animation state.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `80` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.17` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).