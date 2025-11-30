---
title: Glue Shot Projectile Graphics
category: data/projectiles_gfx
---

---

# Glue Shot Projectile Graphics

This document details the graphical assets for the "glue_shot" projectile in Noita, as defined in `glue_shot.xml`.

## Sprite Definition

The primary sprite for the glue shot is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/glue_shot.png` - Specifies the texture file used for the projectile's visuals.
*   **offset\_x**: `4` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `4` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"fireball"` - Sets the initial animation to play.

## Animations

The projectile utilizes a single animation named "fireball".

### RectAnimation: "fireball"

This tag defines a rectangular animation sequence.

#### Key Attributes:

*   **name**: `"fireball"` - The identifier for this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `"4"` - The total number of frames in the animation.
*   **frame\_width**: `"8"` - The width of each individual frame.
*   **frame\_height**: `"8"` - The height of each individual frame.
*   **frame\_wait**: `"0.06"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously.