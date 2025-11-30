---
title: Spark Projectile Graphics
category: projectiles_gfx
---

# Spark Projectile Graphics

This document details the graphical configuration for the "spark" projectile in Noita, as defined in `spark.xml`.

## Sprite Configuration

The primary visual element is a sprite.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/spark.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's anchor point.
*   **offset\_y**: `4.5` - Vertical offset for the sprite's anchor point.

## Animation Configuration

The sprite utilizes a `RectAnimation` for its visual effects.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **frame\_count**: `2` - The total number of frames in the animation.
*   **frame\_width**: `10` - The width of each individual animation frame.
*   **frame\_height**: `10` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally within the sprite sheet.
*   **pos\_x**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - The starting Y-coordinate of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that each frame should be shrunk by one pixel, likely for visual effect or to avoid sprite bleeding.