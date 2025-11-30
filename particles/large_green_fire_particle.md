---
title: Large Green Fire Particle
category: particles
---

---

# Large Green Fire Particle

This document describes the configuration for a large green fire particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/fire_large_green.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `12` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - Sets the default animation to be played.

## Animation: Explosion

The particle utilizes a rectangular animation named "explosion".

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `24` - The width of each individual frame.
*   **frame\_height**: `24` - The height of each individual frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).