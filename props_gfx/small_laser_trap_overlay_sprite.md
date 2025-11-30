---
title: Small Laser Trap Overlay Sprite
category: props_gfx
---

---

# Small Laser Trap Overlay Sprite

This document describes the sprite definition for the small laser trap overlay in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the prop.

### Key Attributes:

*   **filename**: `data/props_gfx/trap_laser_small_overlay.png` - The path to the sprite image file.
*   **offset\_x**: `5` - Horizontal offset for the sprite.
*   **offset\_y**: `5` - Vertical offset for the sprite.
*   **default\_animation**: `"default"` - Specifies the default animation to play.

## Animations

The `<RectAnimation>` element defines the animation frames for the sprite.

### Default Animation (`name="default"`)

This animation is used for the standard visual state of the overlay.

#### Key Attributes:

*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `2` - The total number of frames in the animation.
*   **frame\_width**: `10` - The width of each individual frame.
*   **frame\_height**: `10` - The height of each individual frame.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `2` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).