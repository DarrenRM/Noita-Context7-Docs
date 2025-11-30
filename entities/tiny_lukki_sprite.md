---
title: Tiny Lukki Sprite
category: entities
---

---

# Tiny Lukki Sprite

This document describes the sprite definition for the "tiny lukki" entity in Noita.

## Sprite Definition

The primary sprite for the tiny lukki is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/entities/animals/lukki/lukki_feet/lukki_sprite_tiny.png` - The path to the sprite image file.
*   **offset\_x**: `10` - Horizontal offset for the sprite's position.
*   **offset\_y**: `10` - Vertical offset for the sprite's position.

## Animation: "stand"

The `<RectAnimation>` element defines the animation states for the sprite.

### Key Attributes:

*   **name**: `stand` - The name of this animation state.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `20` - The width of each individual animation frame.
*   **frame\_height**: `20` - The height of each individual animation frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `1` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).