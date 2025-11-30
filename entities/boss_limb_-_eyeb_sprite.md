---
title: Boss Limb - Eyeb Sprite
category: entities
---

# Boss Limb - Eyeb Sprite

This document details the sprite information for the "Eyeb" boss limb entity in Noita, intended for AI-assisted modding.

## Sprite Definition

The `<Sprite>` tag defines the visual appearance and animation frames for the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_limbs/eyeB.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `24` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `24` - Vertical offset of the sprite's origin.

### Animations:

The sprite contains definitions for various animations.

#### `stand` Animation:

*   **name**: `stand`
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in this animation.
*   **frame\_width**: `48` - Width of each individual frame.
*   **frame\_height**: `48` - Height of each individual frame.
*   **frame\_wait**: `0.09` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `6` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for yes, 0 for no).

#### `invisible` Animation:

*   **name**: `invisible`
*   **pos\_x**: `0`
*   **pos\_y**: `48` - This animation starts on the second row of the sprite sheet.
*   **frame\_count**: `1`
*   **frame\_width**: `48`
*   **frame\_height**: `48`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `6`
*   **loop**: `1`

#### `animate` (Walk) Animation:

*   **name**: `animate`
*   **pos\_x**: `0`
*   **pos\_y**: `0` - This animation uses frames from the first row.
*   **frame\_count**: `6` - This animation consists of 6 frames, likely representing movement.
*   **frame\_width**: `48`
*   **frame\_height**: `48`
*   **frame\_wait**: `0.13` - Slightly longer frame wait than static animations.
*   **frames\_per\_row**: `6`
*   **loop**: `0` - This animation is set to not loop, suggesting it plays once.