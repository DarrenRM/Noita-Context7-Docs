---
title: Disc Bullet Trail Particle
category: particles
---

---

# Disc Bullet Trail Particle

This document describes the configuration for the `discbullet_trail.png` particle effect used in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/discbullet_trail.png` - Specifies the image file used for the particle.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The default animation to play when the particle is spawned.

## Animation: `explosion`

This section details the animation sequence for the `explosion` state of the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).