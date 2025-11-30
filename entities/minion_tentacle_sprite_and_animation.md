---
title: Minion Tentacle Sprite and Animation
category: entities
---

# Minion Tentacle Sprite and Animation

This document details the sprite and animation configuration for the "minion_tentacle_1" entity in Noita.

## Sprite Configuration

The primary sprite for the minion tentacle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/special/verlet_chains/minion_tentacle.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation to play by default when the entity is spawned.

## Animation Configuration

The entity utilizes a single animation named "stand".

### Animation Details:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the sprite sheet's top-left corner for this animation.
*   **pos\_y**: `0` - Y-coordinate of the sprite sheet's top-left corner for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `11` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).