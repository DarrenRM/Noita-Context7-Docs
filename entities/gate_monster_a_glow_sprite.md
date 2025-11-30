---
title: Gate Monster A Glow Sprite
category: entities
---

# Gate Monster A Glow Sprite

This document describes the sprite and animation data for the "Gate Monster A Glow" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_gate/gate_monster_a_glow.png` - The image file used for the sprite.
*   **offset\_x**: `28` - Horizontal offset of the sprite.
*   **offset\_y**: `35` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

## Animations

The entity utilizes a single animation defined by the `<RectAnimation>` tag.

### Animation: `stand`

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `56` - The width of each individual frame.
*   **frame\_height**: `70` - The height of each individual frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).