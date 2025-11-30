---
title: Vine Growth Animation
category: data/vegetation
---

---

# Vine Growth Animation

This document describes the XML definition for a vine growth animation in Noita, intended for AI-assisted modding.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the vine growth.

### Key Attributes:

*   **filename**: `data/vegetation/vine_growth_1.png` - Path to the sprite sheet.
*   **offset\_x**: `3` - Horizontal offset for the sprite.
*   **offset\_y**: `1` - Vertical offset for the sprite.
*   **default\_animation**: `vegetation_growth` - Specifies the default animation to play. This is a special name that triggers vegetation growth.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of the animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `7` - Total number of frames in the animation.
*   **frame\_width**: `8` - Width of each individual frame.
*   **frame\_height**: `32` - Height of each individual frame.
*   **frame\_wait**: `1.0` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).