---
title: Orange Directional Blood Splatter Particle
category: particles
---

# Orange Directional Blood Splatter Particle

This documentation describes the configuration for an orange directional blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/bloodsplatters/bloodsplatter_directional_orange_1.png`
    *   Specifies the texture file used for the particle sprite.
*   **offset\_x**: `8`
    *   Horizontal offset of the sprite's origin.
*   **offset\_y**: `8`
    *   Vertical offset of the sprite's origin.
*   **default\_animation**: `smoke`
    *   The name of the default animation to play when the particle is spawned.

## Animation Definition

The particle utilizes a `RectAnimation` to define its visual sequence.

### Key Attributes:

*   **name**: `smoke`
    *   The identifier for this animation, referenced by the `<Sprite>` element.
*   **pos\_x**: `0`
    *   The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0`
    *   The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `5`
    *   The total number of frames in the animation.
*   **frame\_width**: `32`
    *   The width of each individual animation frame.
*   **frame\_height**: `16`
    *   The height of each individual animation frame.
*   **frame\_wait**: `0.025`
    *   The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `8`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).