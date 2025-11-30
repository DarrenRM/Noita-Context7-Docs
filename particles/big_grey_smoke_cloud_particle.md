---
title: Big Grey Smoke Cloud Particle
category: particles
---

---

# Big Grey Smoke Cloud Particle

This document describes the configuration for a "Big Grey Smoke Cloud" particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet for its animation.

### Sprite Attributes

*   **default\_animation**: `explosion` - The name of the default animation to play.
*   **filename**: `data/particles/smoke_cloud_big_grey.png` - The path to the sprite sheet image.
*   **offset\_x**: `12` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.

### RectAnimation: `explosion`

This defines the animation sequence for the smoke cloud.

*   **name**: `explosion` - Identifier for this animation.
*   **frame\_count**: `12` - Total number of frames in the animation.
*   **frame\_height**: `25` - Height of each individual frame in pixels.
*   **frame\_wait**: `0.045` - Time in seconds to wait between frames.
*   **frame\_width**: `25` - Width of each individual frame in pixels.
*   **frames\_per\_row**: `12` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - A flag indicating if frames should shrink by one pixel.