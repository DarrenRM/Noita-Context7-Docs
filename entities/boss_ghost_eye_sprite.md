---
title: Boss Ghost Eye Sprite
category: entities
---

---

# Boss Ghost Eye Sprite

This document describes the sprite definition for the Boss Ghost's eye entity in Noita.

## Sprite Definition

The primary sprite for the Boss Ghost's eye is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_ghost/eye.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - Sets the default animation to play when the entity is spawned.

## Animations

The sprite includes a single animation named "stand".

### Stand Animation:

*   **name**: `"stand"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"1"` - Total number of frames in this animation.
*   **frame\_width**: `"16"` - Width of each individual frame.
*   **frame\_height**: `"16"` - Height of each individual frame.
*   **frame\_wait**: `"0.12"` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `"4"` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop.