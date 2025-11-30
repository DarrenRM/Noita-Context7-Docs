---
title: Tiny Spark Particle
category: particles
---

# Tiny Spark Particle

This document describes the configuration for the "tinyspark_01" particle effect in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The primary visual element of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/tinyspark_01.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `3.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `3.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - Sets the default animation to be played when the particle is spawned.

## Animation Details

The particle utilizes a rectangular animation sequence named "explosion".

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `7` - The width of each individual animation frame in pixels.
*   **frame\_height**: `7` - The height of each individual animation frame in pixels.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation should not loop (play only once).