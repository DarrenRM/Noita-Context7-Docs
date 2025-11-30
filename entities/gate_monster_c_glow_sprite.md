---
title: Gate Monster C Glow Sprite
category: entities
---

# Gate Monster C Glow Sprite

This document describes the sprite and animation data for the "Gate Monster C Glow" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_gate/gate_monster_c_glow.png` - The path to the sprite image file.
*   **offset\_x**: `18` - Horizontal offset for the sprite.
*   **offset\_y**: `26` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The entity utilizes a single animation defined within the `<Sprite>` tag.

### `stand` Animation:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `41` - The width of each individual frame.
*   **frame\_height**: `75` - The height of each individual frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).