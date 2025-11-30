---
title: Arrow Projectile Graphics
category: projectiles_gfx
---

---

# Arrow Projectile Graphics

This document describes the graphical assets for the "arrow" projectile in Noita, as defined in `arrow.xml`.

## Sprite Definition

The primary sprite for the arrow projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/arrow.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `3.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `2.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the default animation to play.

## Animations

The projectile utilizes a single animation named "fireball".

### RectAnimation: `fireball`

This tag defines a rectangular animation sequence.

#### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `9` - The width of each individual frame.
*   **frame\_height**: `5` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).