---
title: Verlet Chain Banner Part 4 Sprite
category: entities
---

# Verlet Chain Banner Part 4 Sprite

This document describes the sprite component for the fourth part of averlet chain banner entity in Noita.

## Entity Structure

The entity primarily consists of a `SpriteComponent`.

## SpriteComponent

This component defines the visual representation of the banner part.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite.
    *   Value: `"data/entities/verlet_chains/banner/parts/image_4.xml"`
*   **`offset_x`**: The horizontal offset of the sprite from its entity's origin.
    *   Value: `"1"`
*   **`offset_y`**: The vertical offset of the sprite from its entity's origin.
    *   Value: `"12"`
*   **`z_index`**: Determines the rendering order of the sprite. Lower values are rendered behind higher values.
    *   Value: `"-1.44"`
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   Value: `"0"` (Disabled)