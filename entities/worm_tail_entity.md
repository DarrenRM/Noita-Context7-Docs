---
title: Worm Tail Entity
category: entities
---

# Worm Tail Entity

This document describes the `worm_tail.xml` entity, which defines the visual and behavioral aspects of a worm's tail segment in Noita.

## Sprite

The `Sprite` element defines the visual representation of the worm tail.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_tail.png` - Path to the sprite image.
*   **offset_x**: `15` - Horizontal offset for the sprite.
*   **offset_y**: `6` - Vertical offset for the sprite.
*   **default_animation**: `"stand"` - The animation to play by default.

### Animations:

*   **stand**:
    *   **frame\_count**: `1` - Number of frames in the animation.
    *   **frame\_height**: `12` - Height of each animation frame.
    *   **frame\_wait**: `0.082` - Delay between frames in seconds.
    *   **frame\_width**: `14` - Width of each animation frame.
    *   **frames\_per\_row**: `1` - Number of frames per row in the sprite sheet.
    *   **name**: `"stand"` - The name of this animation.
    *   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
    *   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.