---
title: Laser Gate Right Sprite
category: data/buildings_gfx
---

# Laser Gate Right Sprite

This document describes the sprite definition for the "lasergate_right" building graphic in Noita.

## Sprite Definition

The primary `<Sprite>` element defines the visual asset for the laser gate.

### Key Attributes

*   **filename**: `data/buildings_gfx/lasergate_right.png` - Specifies the path to the sprite image file.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `4` - Vertical offset of the sprite.
*   **default\_animation**: `fireball` - Sets the default animation to play when the sprite is active.

## Animations

The sprite includes a single animation definition.

### `fireball` Animation

This animation defines the visual sequence for the laser gate's "fireball" state.

#### Key Attributes

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `8` - The height of each individual frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously.