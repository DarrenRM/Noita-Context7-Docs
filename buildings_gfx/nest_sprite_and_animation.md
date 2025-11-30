---
title: Nest Sprite and Animation
category: data/buildings_gfx
---

# Nest Sprite and Animation

This document describes the sprite and animation data for the "nest" building in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the nest is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/buildings_gfx/nest.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the sprite is active.

## Animation: "stand"

The `"stand"` animation defines the visual sequence for the nest.

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X-coordinate within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y-coordinate within the sprite sheet for this animation.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `32` - The height of each individual frame.
*   **frame\_wait**: `0.15` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).