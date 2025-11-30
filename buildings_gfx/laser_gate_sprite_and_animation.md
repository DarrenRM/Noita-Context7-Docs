---
title: Laser Gate Sprite and Animation
category: data/buildings_gfx
---

# Laser Gate Sprite and Animation

This document describes the sprite and animation data for the Laser Gate building in Noita, as defined in `lasergate.xml`.

## Sprite Definition

The primary sprite for the Laser Gate is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/buildings_gfx/lasergate.png` - Specifies the image file used for the sprite.
*   **offset_x**: `4` - Horizontal offset of the sprite.
*   **offset_y**: `4` - Vertical offset of the sprite.
*   **default_animation**: `fireball` - The name of the animation that plays by default.

## Animation Definition

The Laser Gate utilizes a `RectAnimation` for its visual representation.

### Animation: `fireball`

This animation defines the sequence of frames for the Laser Gate's visual effect.

#### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `8` - The width of each individual animation frame.
*   **frame_height**: `8` - The height of each individual animation frame.
*   **frame_wait**: `0.05` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).