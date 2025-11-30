---
title: Blast Regeneration Projectile Graphics
category: projectiles_gfx
---

# Blast Regeneration Projectile Graphics

This document details the graphical assets for the "blast_regeneration" projectile in Noita, focusing on its sprite and animation definitions.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/blast.png` - Specifies the texture file used for the sprite.
*   **offset\_x**, **offset\_y**: `32`, `32` - Defines the center point of the sprite relative to its origin.
*   **color\_r**, **color\_g**, **color\_b**, **color\_a**: `0.7`, `1`, `0.6`, `1` - Sets the red, green, blue, and alpha (transparency) color components of the sprite. This results in a greenish-yellow tint.
*   **default\_animation**: `spawn` - Indicates the animation to play by default when the projectile is created.

## Animations

The projectile utilizes multiple `RectAnimation` blocks to define different animation sequences.

### `spawn` Animation

This animation is the default and plays when the projectile is first created.

#### Key Attributes:

*   **name**: `spawn` - The identifier for this animation.
*   **frame\_count**: `5` - The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: `65`, `65` - The dimensions of each individual frame in pixels.
*   **frames\_per\_row**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **loop**: `0` - Indicates that this animation does not loop.
*   **next\_animation**: `fireball` - The animation to transition to after this one completes.
*   **pos\_x**, **pos\_y**: `0`, `1` - The starting X and Y coordinates (in pixels) of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - A flag indicating if frames should shrink by one pixel each iteration.

### `fireball` Animation

This animation plays after the `spawn` animation completes.

#### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **frame\_count**: `5` - The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: `65`, `65` - The dimensions of each individual frame in pixels.
*   **frames\_per\_row**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.01` - The duration (in seconds) each frame is displayed before advancing. This is faster than the `spawn` animation.
*   **pos\_x**, **pos\_y**: `0`, `66` - The starting X and Y coordinates (in pixels) of the animation frames within the sprite sheet. This indicates these frames are located on the next row of the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - A flag indicating if frames should shrink by one pixel each iteration.