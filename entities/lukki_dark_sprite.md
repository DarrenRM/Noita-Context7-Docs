---
title: Lukki Dark Sprite
category: entities
---

# Lukki Dark Sprite

This document describes the sprite data for the "Lukki Dark" entity's feet in Noita. It defines the visual appearance and animation for this specific part of the creature.

## Sprite Definition

The core of this data is the `<Sprite>` element, which specifies the image file and its default animation.

### Key Attributes:

*   **filename**: `data/entities/animals/lukki/lukki_feet/lukki_dark_sprite.png` - The path to the sprite image file.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `16` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The name of the animation that plays by default.

## Animations

The `<Sprite>` element contains one or more `<RectAnimation>` elements, defining different animations.

### `stand` Animation

This animation defines the "standing" pose for the Lukki's dark feet.

#### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `"0"` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"32"` - The width of each individual frame.
*   **frame\_height**: `"32"` - The height of each individual frame.
*   **frame\_wait**: `"0.04"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously (1 for true, 0 for false).