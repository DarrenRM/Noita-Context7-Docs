---
title: Green Verlet Chain Segment (4)
category: entities
---

# Green Verlet Chain Segment (4)

This entity represents a single segment of the green Verlet chain used by a boss centipede. It's a visual component with basic animation.

## Sprite

Defines the visual appearance and animation of the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/verlet_piece_4_green.png` - Path to the sprite image.
*   **offset\_x**, **offset\_y**: `0` - Position offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Animation: `stand`

A simple, static animation for the segment.

*   **name**: `"stand"`
*   **pos\_x**, **pos\_y**: `0` - Starting position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - Number of frames in the animation.
*   **frame\_width**, **frame\_height**: `7` - Dimensions of each animation frame.
*   **frame\_wait**: `1` - Delay between frames (in this case, effectively no delay as there's only one frame).
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Whether the animation should loop (1 for true, 0 for false).