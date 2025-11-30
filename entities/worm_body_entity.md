---
title: Worm Body Entity
category: entities
---

---

# Worm Body Entity

This document describes the `worm_body.xml` entity, a component of the Noita worm. It focuses on key attributes relevant to AI-assisted modding.

## Sprite

The `Sprite` element defines the visual representation of the worm body.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_body.png` - Path to the sprite image.
*   **offset_x**: `15` - Horizontal offset for the sprite.
*   **offset_y**: `6` - Vertical offset for the sprite.
*   **default_animation**: `"stand"` - The animation to play by default.

### Animations:

*   **stand**:
    *   **frame\_count**: `1` - Number of frames in the animation.
    *   **frame\_height**: `12` - Height of each animation frame.
    *   **frame\_wait**: `0.082` - Delay between frames in seconds.
    *   **frame\_width**: `14` - Width of each animation frame.
    *   **frames\_per\_row**: `1` - Number of frames in a single row of the sprite sheet.
    *   **name**: `"stand"` - The name of this animation.
    *   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
    *   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.