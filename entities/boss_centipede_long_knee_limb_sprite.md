---
title: Boss Centipede Long Knee Limb Sprite
category: entities
---

# Boss Centipede Long Knee Limb Sprite

This documentation describes the sprite and animation data for the "long knee" limb of the boss centipede in Noita.

## Sprite

The `Sprite` element defines the visual appearance and default animation for the limb.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/limbs/limb_long_knee.png` - The path to the sprite image file.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `8` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The name of the animation to play by default.

## Animations

The `RectAnimation` element defines a specific animation sequence.

### `stand` Animation:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).