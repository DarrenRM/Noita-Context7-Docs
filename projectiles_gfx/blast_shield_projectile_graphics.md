---
title: Blast Shield Projectile Graphics
category: projectiles_gfx
---

---

# Blast Shield Projectile Graphics

This document details the graphical assets for the "blast_shield" projectile in Noita, as defined in `blast_shield.xml`.

## Sprite Definition

The primary sprite definition for the blast shield projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/blast.png` - The texture file used for the sprite.
*   **offset\_x**: `32` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - Vertical offset of the sprite's origin.
*   **color\_r, color\_g, color\_b, color\_a**: Define the base color tint of the sprite (Red, Green, Blue, Alpha).

## Animations

The sprite utilizes multiple `RectAnimation` elements to define different visual states.

### Animation: `spawn`

The initial animation sequence when the projectile is created.

#### Key Attributes:

*   **name**: `spawn`
*   **frame\_count**: `5` - Total number of frames in this animation.
*   **frame\_width**: `65` - Width of each individual frame.
*   **frame\_height**: `65` - Height of each individual frame.
*   **frames\_per\_row**: `5` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.02` - Time in seconds to wait between frames.
*   **loop**: `0` - Indicates this animation does not loop.
*   **next\_animation**: `fireball` - The animation to transition to after `spawn` completes.
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates frames shrink by one pixel each step.

### Animation: `fireball`

The main animation sequence for the projectile while in flight.

#### Key Attributes:

*   **name**: `fireball`
*   **frame\_count**: `5` - Total number of frames in this animation.
*   **frame\_width**: `65` - Width of each individual frame.
*   **frame\_height**: `65` - Height of each individual frame.
*   **frames\_per\_row**: `5` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.01` - Time in seconds to wait between frames.
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `66` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates frames shrink by one pixel each step.