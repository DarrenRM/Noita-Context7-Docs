---
title: Waterstone Bubble Particle
category: particles
---

# Waterstone Bubble Particle

This document describes the configuration for the `waterstone_bubble.xml` particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for the waterstone bubble is defined here.

### Key Attributes:

*   **filename**: `data/particles/waterstone_bubble.png` - Specifies the image file used for the particle.
*   **offset\_x**: `7` - Horizontal offset for the sprite.
*   **offset\_y**: `7` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - Sets the default animation to play when the particle is spawned.

### Animation: `explosion`

This section details the animation sequence for the `explosion` state.

#### Key Attributes:

*   **name**: `explosion` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `14` - The height of each individual frame.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).