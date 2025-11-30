---
title: Worm Head Entity
category: entities
---

# Worm Head Entity

This document describes the `worm_head.xml` entity, which defines the visual representation and animations for the head of a worm in Noita.

## Sprite

The `Sprite` element defines the graphical assets for the worm head.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_head.png` - Specifies the texture file used for the worm head.
*   **offset_x**: `5` - Horizontal offset for the sprite.
*   **offset_y**: `7` - Vertical offset for the sprite.
*   **default_animation**: `"stand"` - The animation to play by default when the entity is spawned.

### Animations:

The `Sprite` element contains `RectAnimation` elements, defining different animation sequences.

#### `eat` Animation:

*   **name**: `"eat"`
*   **frame\_count**: `7` - Total number of frames in the animation.
*   **frame\_height**: `13` - Height of each animation frame.
*   **frame\_wait**: `0.082` - Time in seconds to wait between frames.
*   **frame\_width**: `17` - Width of each animation frame.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel.

#### `stand` Animation:

*   **name**: `"stand"`
*   **frame\_count**: `7` - Total number of frames in the animation.
*   **frame\_height**: `13` - Height of each animation frame.
*   **frame\_wait**: `0.082` - Time in seconds to wait between frames.
*   **frame\_width**: `17` - Width of each animation frame.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel.