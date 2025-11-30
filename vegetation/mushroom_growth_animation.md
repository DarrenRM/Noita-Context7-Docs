---
title: Mushroom Growth Animation
category: data
---

# Mushroom Growth Animation

This XML file defines the visual animation for a growing mushroom in Noita. It's used to create a dynamic visual effect for vegetation.

## Sprite Definition

The primary element is the `<Sprite>` tag, which links to the image file and defines its animation.

### Key Attributes:

*   **filename**: `data/vegetation/mushroom_growth_2.png` - Path to the sprite sheet.
*   **offset\_x**: `12` - Horizontal offset for the sprite.
*   **offset\_y**: `33` - Vertical offset for the sprite.
*   **default\_animation**: `vegetation_growth` - Specifies the default animation to play.

## Animation Details

The `<RectAnimation>` tag defines the specific frames and timing for the `vegetation_growth` animation.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `34` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

**Note:** The comment `<!-- vegetation_growth is special name, creates a growing vegetation with it -->` highlights that this animation name is specifically recognized by the game engine to trigger a growing vegetation effect.