---
title: Large Blue Blood Splatter 3 Particle
category: particles
---

---

# Large Blue Blood Splatter 3 Particle

This document describes the configuration for a specific particle effect in Noita, representing a large blue blood splatter.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/bloodsplatters/bloodsplatter_large_blue_3.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `16` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"smoke"` - The name of the default animation to play when the particle is spawned.

## Animation Details

The particle utilizes a `RectAnimation` to define its visual sequence.

### Key Attributes:

*   **name**: `"smoke"` - The identifier for this animation, referenced by `default_animation` in the `<Sprite>` tag.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `33` - The width of each individual frame in pixels.
*   **frame\_height**: `33` - The height of each individual frame in pixels.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally within the sprite sheet.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: `1` - The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - A flag indicating that each frame should shrink by one pixel after each animation cycle (likely intended for fading or shrinking effects).