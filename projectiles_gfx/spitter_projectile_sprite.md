---
title: Spitter Projectile Sprite
category: projectiles_gfx
---

---

# Spitter Projectile Sprite

This documentation describes the sprite and animation data for the "spitter" projectile in Noita.

## Sprite Definition

The main `<Sprite>` element defines the visual asset for the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/spitter.png` - The path to the sprite sheet image.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `6` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to play by default.

## Animation Definition

The `<RectAnimation>` element defines how the sprite sheet is used to create an animation.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual animation frame.
*   **frame\_height**: `12` - The height of each individual animation frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes). In this case, it does not loop.