---
title: Electric Spark Particle
category: particles
---

---

# Electric Spark Particle

This document describes the configuration for the `spark_electric.xml` particle effect in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The primary sprite for the electric spark is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/spark_electric.png` - Specifies the image file used for the particle's visual.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to be played by default.

## Animation: Explosion

The `<RectAnimation>` tag defines the "explosion" animation, which dictates how the sprite frames are displayed over time.

### Key Attributes:

*   **name**: `explosion` - Identifies this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `6` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).