---
title: Minion Physics Eye Sprite
category: entities
---

# Minion Physics Eye Sprite

This document describes the sprite and animation data for the "Minion Physics Eye" entity in Noita.

## Sprite

The main sprite for the Minion Physics Eye is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/minion_physics_eye.png` - Specifies the texture file used for the sprite.
*   **default\_animation**: `"stare"` - Sets the initial animation to play when the entity is spawned.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.

## RectAnimation: "stare"

This section defines the "stare" animation, which is the default animation for this entity.

### Key Attributes:

*   **name**: `"stare"` - The name of this animation.
*   **frame\_count**: `12` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `20` - The height of each individual frame.
*   **frames\_per\_row**: `12` - The number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **loop**: `1` - Indicates that the animation should loop continuously.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.