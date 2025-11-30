---
title: Spark Glitter Particle
category: particles
---

# Spark Glitter Particle

This document describes the configuration for the "spark_glitter" particle effect in Noita, used for visual effects.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/spark_glitter.png` - Specifies the texture file used for the particle sprite.
*   **offset\_x**: `2` - Horizontal offset for the sprite.
*   **offset\_y**: `2` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to be used by default.

## Animation: Explosion

The `RectAnimation` element defines a specific animation sequence for the sprite.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `6` - The total number of frames in this animation.
*   **frame\_width**: `5` - The width of each individual animation frame.
*   **frame\_height**: `5` - The height of each individual animation frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).