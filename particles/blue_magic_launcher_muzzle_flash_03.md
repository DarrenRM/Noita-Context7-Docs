---
title: Blue Magic Launcher Muzzle Flash 03
category: particles
---

# Blue Magic Launcher Muzzle Flash 03

This documentation describes the `muzzle_magic_launcher_blue_03.xml` file, which defines a muzzle flash particle effect for the game Noita.

## Sprite Definition

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_blue_03.png`
    *   Specifies the image file used for the particle's texture.
*   **offset\_x**: `8`
    *   Horizontal offset of the sprite's origin.
*   **offset\_y**: `7`
    *   Vertical offset of the sprite's origin.
*   **default\_animation**: `"muzzle"`
    *   The name of the default animation to play for this sprite.

## Animation Definition

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **name**: `"muzzle"`
    *   The identifier for this animation, referenced by the `<Sprite>` element.
*   **frame\_count**: `1`
    *   The total number of frames in the animation.
*   **frame\_width**: `16`
    *   The width of each individual frame in pixels.
*   **frame\_height**: `16`
    *   The height of each individual frame in pixels.
*   **frame\_wait**: `0.1`
    *   The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).

This configuration creates a simple, single-frame muzzle flash effect that plays once.