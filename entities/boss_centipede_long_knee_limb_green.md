---
title: Boss Centipede Long Knee Limb (Green)
category: entities
---

```

# Boss Centipede Long Knee Limb (Green)

This document describes the `limb_long_knee_green.xml` entity, which defines a visual component for the boss centipede's limbs.

## Sprite

The primary visual representation of this limb segment.

*   **filename**: `data/entities/animals/boss_centipede/limbs/limb_long_knee_green.png` - The texture file for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - Vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Animations

#### `stand`

This animation defines the visual frames for the limb segment when it is in a standing or idle state.

*   **name**: `"stand"`
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).