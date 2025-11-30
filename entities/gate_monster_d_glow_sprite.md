---
title: Gate Monster D Glow Sprite
category: entities
---

# Gate Monster D Glow Sprite

This document describes the sprite definition for the "Gate Monster D Glow" entity in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_gate/gate_monster_d_glow.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

### Animations:

The `Sprite` element contains one or more `RectAnimation` elements, defining different animation states.

#### `stand` Animation:

*   **name**: `"stand"` - The name of this animation state.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `65` - The width of each individual animation frame.
*   **frame\_height**: `65` - The height of each individual animation frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).