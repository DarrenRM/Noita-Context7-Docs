---
title: Meat Maggot Head Sprite
category: entities
---

# Meat Maggot Head Sprite

This document describes the sprite data for the Meat Maggot's head in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the visual representation and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/meatmaggot_head.png` - The path to the sprite image file.
*   **offset\_x**: `5` - Horizontal offset for the sprite.
*   **offset\_y**: `4.5` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The sprite includes definitions for different animations.

### `stand` Animation

*   **name**: `"stand"`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in this animation.
*   **frame\_width**: `10` - Width of each individual frame.
*   **frame\_height**: `9` - Height of each individual frame.
*   **frame\_wait**: `0.082` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).

### `eat` Animation

*   **name**: `"eat"`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `1`
*   **frame\_width**: `10`
*   **frame\_height**: `9`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `1`
*   **loop**: `1`