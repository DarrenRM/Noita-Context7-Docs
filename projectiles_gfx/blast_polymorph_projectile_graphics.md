---
title: Blast Polymorph Projectile Graphics
category: projectiles_gfx
---

# Blast Polymorph Projectile Graphics

This XML file defines the graphical assets for the "blast_polymorph" projectile in Noita. It specifies the sprite sheet, color tinting, and animations used for this projectile.

## Sprite Attributes

The `<Sprite>` tag defines the base visual properties of the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/blast.png` - The path to the sprite sheet image file.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **color\_r**, **color\_g**, **color\_b**, **color\_a**: These attributes define a color tint applied to the sprite. In this case, it's a yellowish-white tint (`1`, `0.9`, `0.6`, `1`).
*   **default\_animation**: `spawn` - The animation that plays by default when the projectile is created.

## Animations

The `<RectAnimation>` tags define different animation sequences within the sprite sheet.

### `spawn` Animation

This animation is used when the projectile is initially created.

#### Key Attributes:

*   **name**: `spawn`
*   **frame\_count**: `5` - The total number of frames in this animation.
*   **frame\_width**: `65` - The width of each individual frame.
*   **frame\_height**: `65` - The height of each individual frame.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **loop**: `0` - Indicates that this animation does not loop.
*   **next\_animation**: `fireball` - The animation to transition to after this one completes.
*   **pos\_x**: `0` - The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - The vertical starting position of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that frames shrink by one pixel each.

### `fireball` Animation

This animation is played after the `spawn` animation finishes.

#### Key Attributes:

*   **name**: `fireball`
*   **frame\_count**: `5` - The total number of frames in this animation.
*   **frame\_width**: `65` - The width of each individual frame.
*   **frame\_height**: `65` - The height of each individual frame.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.01` - The duration (in seconds) each frame is displayed before advancing.
*   **pos\_x**: `0` - The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: `66` - The vertical starting position of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that frames shrink by one pixel each.