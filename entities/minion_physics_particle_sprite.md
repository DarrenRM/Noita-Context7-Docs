---
title: Minion Physics Particle Sprite
category: entities
---

# Minion Physics Particle Sprite

This document describes the sprite configuration for the "Minion Physics Particle" entity in Noita. This entity is likely used as a visual effect or component for a larger boss creature, such as the centipede.

## Sprite

The primary sprite definition for this particle.

### Key Attributes:

*   **default\_animation**: Specifies the default animation to play, which is "fade" in this case.
*   **filename**: The path to the sprite image file.
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.

### RectAnimation

Defines the parameters for a rectangular sprite animation.

#### Key Attributes:

*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frame\_width**: The width of each individual frame.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should loop (0 for no loop, 1 for loop).
*   **name**: The name of this animation, referenced by `default_animation`.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.