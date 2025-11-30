---
title: Lukki Feet Emissive Sprite B
category: entities
---

# Lukki Feet Emissive Sprite B

This document describes the sprite data for the emissive variant of the Lukki's feet.

## Sprite

The primary sprite definition for this entity.

### Key Attributes:

*   **filename**: `data/entities/animals/lukki/lukki_feet/lukki_sprite_emissive_b.png` - The path to the sprite image file.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.

## RectAnimation

Defines the animation for the sprite.

### Key Attributes:

*   **name**: `stand` - The name of this animation state.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `20` - The width of a single animation frame.
*   **frame\_height**: `20` - The height of a single animation frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).