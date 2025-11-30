---
title: Boss Centipede Long Limb B Sprite
category: entities
---

# Boss Centipede Long Limb B Sprite

This document describes the sprite and animation data for the "Long Limb B" part of the Boss Centipede in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/limbs/limb_long_B.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `8` - Vertical offset of the sprite.

## RectAnimation: "stand"

This section defines the animation sequence for the "stand" state of the limb.

### Key Attributes:

*   **name**: `stand` - The name of this animation state.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `80` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.17` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `8` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.