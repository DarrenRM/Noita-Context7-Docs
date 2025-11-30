---
title: Minion Tentacle 1 Sprite
category: entities
---

# Minion Tentacle 1 Sprite

This document describes the sprite and animation data for the "minion_tentacle_1" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/minion_tentacle.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

## Animation

The entity utilizes a single animation named "stand".

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the sprite's top-left corner within the texture.
*   **pos\_y**: `0` - Y-coordinate of the sprite's top-left corner within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `11` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop indefinitely.