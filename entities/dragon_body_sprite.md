---
title: Dragon Body Sprite
category: entities
---

# Dragon Body Sprite

This document describes the sprite definition for the dragon's body in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The primary sprite for the dragon's body is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/dragon_body.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `17` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `15` - Vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the sprite is active.

## Animations

The sprite supports various animations, with the "eat" animation detailed below.

### `eat` Animation

This animation is used for the dragon's eating action.

#### Key Attributes:

*   **name**: `"eat"` - The identifier for this animation.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_height**: `33` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frame\_width**: `33` - The width of each individual frame in pixels.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that each frame should be shrunk by one pixel, likely for visual effect or to avoid sprite bleeding.