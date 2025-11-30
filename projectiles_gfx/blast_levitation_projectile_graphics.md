---
title: Blast Levitation Projectile Graphics
category: projectiles_gfx
---

# Blast Levitation Projectile Graphics

This document details the graphical assets for the "blast_levitation" projectile in Noita, focusing on its sprite and animation definitions.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/blast.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `32` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `32` - Vertical offset for the sprite's origin.
*   **color\_r**, **color\_g**, **color\_b**, **color\_a**: These attributes define the tint of the sprite.
    *   `color_r`: `1` (Red component)
    *   `color_g`: `0.7` (Green component)
    *   `color_b`: `0.2` (Blue component)
    *   `color_a`: `1` (Alpha/Transparency component)
*   **default\_animation**: `spawn` - The animation to play by default when the projectile is created.

## Animations

The projectile utilizes multiple `RectAnimation` definitions to control its visual behavior over time.

### `spawn` Animation

This animation is the initial visual state of the projectile.

#### Key Attributes:

*   **name**: `spawn` - Identifier for this animation.
*   **frame\_count**: `5` - Total number of frames in this animation.
*   **frame\_width**: `65` - Width of each individual frame in pixels.
*   **frame\_height**: `65` - Height of each individual frame in pixels.
*   **frames\_per\_row**: `5` - Number of frames arranged horizontally in the texture.
*   **frame\_wait**: `0.02` - Time in seconds to wait between frames.
*   **loop**: `0` - Indicates that this animation does not loop.
*   **next\_animation**: `fireball` - The animation to transition to after this one completes.
*   **pos\_x**: `0` - X-coordinate offset within the sprite sheet for this animation's frames.
*   **pos\_y**: `1` - Y-coordinate offset within the sprite sheet for this animation's frames.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that frames shrink by one pixel each iteration.

### `fireball` Animation

This animation represents the projectile's main visual state after the initial spawn.

#### Key Attributes:

*   **name**: `fireball` - Identifier for this animation.
*   **frame\_count**: `5` - Total number of frames in this animation.
*   **frame\_width**: `65` - Width of each individual frame in pixels.
*   **frame\_height**: `65` - Height of each individual frame in pixels.
*   **frames\_per\_row**: `5` - Number of frames arranged horizontally in the texture.
*   **frame\_wait**: `0.01` - Time in seconds to wait between frames.
*   **pos\_x**: `0` - X-coordinate offset within the sprite sheet for this animation's frames.
*   **pos\_y**: `66` - Y-coordinate offset within the sprite sheet for this animation's frames.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that frames shrink by one pixel each iteration.