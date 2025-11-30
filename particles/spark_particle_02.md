---
title: Spark Particle 02
category: particles
---

---

# Spark Particle 02

This document describes the configuration for `spark_02.xml`, a particle effect in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/spark_02.png` - Specifies the image file used for the particle's visual representation.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `8` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation that plays by default when this particle is spawned.

## Animation: Explosion

The `<RectAnimation>` tag defines the "explosion" animation.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `3` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `3` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop. `0` means it will not loop (play once).