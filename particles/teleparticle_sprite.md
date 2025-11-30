---
title: Teleparticle Sprite
category: particles
---

# Teleparticle Sprite

This document describes the sprite and animation data for the "teleparticle" in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the teleparticle.

### Key Attributes:

*   **filename**: `data/particles/teleparticle.png` - The texture file used for the sprite.
*   **offset\_x**: `1.5` - Horizontal offset for the sprite.
*   **offset\_y**: `4` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animations

### `explosion` Animation

This animation defines the visual sequence for the teleparticle's explosion effect.

#### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `3` - The width of each individual frame.
*   **frame\_height**: `8` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).