---
title: Grass Patch 06 Sprite
category: data/vegetation
---

---

# Grass Patch 06 Sprite

This document describes the sprite data for `grass_patch_06.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/grass_patch_06.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `10` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `9` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The animation to play by default. This is a special name indicating a growing vegetation effect.

## Animation: `vegetation_growth`

This animation defines the visual appearance and behavior of the growing grass patch.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - The X position of the animation's starting frame within the sprite sheet.
*   **pos\_y**: `0` - The Y position of the animation's starting frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each individual frame.
*   **frame\_height**: `10` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

This animation is designed to create a simple, static visual for a grass patch, with a single frame and a defined growth duration.