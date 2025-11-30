---
title: Lukki Wiggle Sprite
category: entities
---

---

# Lukki Wiggle Sprite

This documentation describes the sprite used for the "wiggle" animation of the Lukki creature in Noita.

## Sprite

The primary sprite definition for the Lukki's wiggle animation.

### Key Attributes:

*   **filename**: `data/entities/animals/lukki/lukki_feet/lukki_wiggle.png` - The path to the sprite image file.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## RectAnimation: "stand"

Defines the "stand" animation, which is used for the Lukki's wiggle.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `20` - The width of each individual frame.
*   **frame\_height**: `20` - The height of each individual frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).