---
title: Statue Physics Emissive Sprite
category: entities/enemies_gfx
---

# Statue Physics Emissive Sprite

This document describes the sprite definition for the "statue_physics_emissive" enemy in Noita. It details the visual representation and animation properties.

## Sprite Definition

The primary sprite for this enemy is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/statue_physics_emissive.png` - The path to the sprite image file.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `13` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the entity is spawned.

## Animations

The sprite supports at least one animation, "stand".

### `stand` Animation:

This animation defines the default visual state of the statue.

#### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `"0"` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `"0"` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"16"` - The width of each individual animation frame.
*   **frame\_height**: `"24"` - The height of each individual animation frame.
*   **frame\_wait**: `"0.14"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `"1"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop indefinitely (1 for true, 0 for false).