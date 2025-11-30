---
title: Tiny Spark 02 Particle
category: particles
---

---

# Tiny Spark 02 Particle

This document describes the configuration for the `tinyspark_02` particle effect in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The primary visual element is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/tinyspark_02.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `3.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `3.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation Details

The particle utilizes a rectangular animation sequence.

### `explosion` Animation:

*   **name**: `explosion` - Identifies this specific animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `7` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `0.06` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).