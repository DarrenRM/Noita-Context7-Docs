---
title: Blast Out Levitation Particle
category: particles
---

# Blast Out Levitation Particle

This documentation describes the `blast_out_levitation.xml` particle effect, used for visual feedback in Noita.

## Sprite

The primary visual component of the particle.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - The texture file used for the particle.
*   **offset\_x**: `32` - Horizontal offset for the sprite.
*   **offset\_y**: `32` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The animation to play by default.
*   **color\_r**: `1` - Red component of the particle's color.
*   **color\_g**: `0.7` - Green component of the particle's color.
*   **color\_b**: `0.2` - Blue component of the particle's color.

### Animation: `explosion`

Defines the animation sequence for the particle.

#### Key Attributes:

*   **name**: `explosion` - The name of this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `64` - The width of each individual frame.
*   **frame\_height**: `64` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).