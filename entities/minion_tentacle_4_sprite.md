---
title: Minion Tentacle 4 Sprite
category: entities
---

---

# Minion Tentacle 4 Sprite

This documentation describes the sprite and animation data for the "minion_tentacle_4" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/special/verlet_chains/minion_tentacle.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation: "stand"

The "stand" animation is a simple, single-frame animation.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `12` - The X-coordinate of the sprite frame within the texture.
*   **pos\_y**: `0` - The Y-coordinate of the sprite frame within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each frame.
*   **frame\_height**: `11` - The height of each frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).