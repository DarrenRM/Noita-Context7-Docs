---
title: Slime Burst Explosion Particle
category: particles
---

---

# Slime Burst Explosion Particle

This document describes the `explosion_032_slimeburst.xml` particle, used to create a slime burst explosion effect in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   **default\_animation**: Specifies the default animation to play, which is "explosion" in this case.
*   **filename**: The path to the sprite sheet used for the animation.
*   **offset\_x**: The horizontal offset of the sprite's origin.
*   **offset\_y**: The vertical offset of the sprite's origin.

### RectAnimation

The `RectAnimation` element defines the specific animation sequence.

#### Key Attributes:

*   **name**: The name of the animation, "explosion".
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **loop**: Determines if the animation should loop (0 for no loop, 1 for loop).
*   **pos\_x**: The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y position of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: A flag indicating if frames should shrink by one pixel each iteration.