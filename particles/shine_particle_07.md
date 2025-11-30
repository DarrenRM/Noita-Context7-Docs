---
title: Shine Particle 07
category: particles
---

---

# Shine Particle 07

This document describes the configuration for `shine_07.xml`, a particle effect in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/shine_07.png` - Specifies the image file used for the particle.
*   **offset\_x**: `7.5` - Horizontal offset for the sprite.
*   **offset\_y**: `7.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The default animation to play when this sprite is used.

## Animation: Explosion

The `explosion` animation defines how the sprite is displayed over time.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `15` - The width of each individual frame.
*   **frame\_height**: `15` - The height of each individual frame.
*   **frame\_wait**: `0.06` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `9` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).