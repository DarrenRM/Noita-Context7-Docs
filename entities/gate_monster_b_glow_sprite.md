---
title: Gate Monster B Glow Sprite
category: entities
---

---

# Gate Monster B Glow Sprite

This document describes the sprite configuration for the "Gate Monster B Glow" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_gate/gate_monster_b_glow.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `28` - The horizontal offset of the sprite from its origin.
*   **offset\_y**: `35` - The vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

## Animations

The entity utilizes a single animation named "stand".

### RectAnimation: "stand"

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `41` - The width of each individual animation frame.
*   **frame\_height**: `75` - The height of each individual animation frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `1` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).