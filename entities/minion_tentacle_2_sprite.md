---
title: Minion Tentacle 2 Sprite
category: entities
---

# Minion Tentacle 2 Sprite

This document describes the sprite and animation data for the "minion_tentacle_2" entity, likely a segment of a larger boss creature.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/minion_tentacle.png` - The image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

## Animation: `stand`

The `stand` animation is defined using the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `4` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `11` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).