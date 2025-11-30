---
title: HPCrystal Sprite
category: data/buildings_gfx
---

# HPCrystal Sprite

This document describes the sprite definition for the HPCrystal entity in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the HPCrystal.

### Key Attributes

*   **filename**: `data/buildings_gfx/hpcrystal.png` - The path to the sprite image file.
*   **offset\_x**: `13` - Horizontal offset of the sprite.
*   **offset\_y**: `23` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

### Stand Animation

The `<RectAnimation>` element defines the "stand" animation.

#### Key Attributes

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `18` - The total number of frames in the animation.
*   **frame\_width**: `26` - The width of each individual frame.
*   **frame\_height**: `26` - The height of each individual frame.
*   **frame\_wait**: `0.13` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `18` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).