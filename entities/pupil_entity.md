---
title: Pupil Entity
category: entities
---

---

# Pupil Entity

This document describes the `pupil.xml` entity, which represents a visual element likely used for a boss's eye or a similar targeting indicator in Noita.

## Sprite

The `Sprite` element defines the visual appearance and animation of the pupil.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_ghost/pupil.png` - Specifies the texture file for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Animations:

#### `stand` Animation

*   **name**: `"stand"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"1"` - Number of frames in this animation.
*   **frame\_width**: `"16"` - Width of each frame.
*   **frame\_height**: `"16"` - Height of each frame.
*   **frame\_wait**: `"0.12"` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `"4"` - Number of frames in a single row of the sprite sheet.
*   **loop**: `"1"` - Indicates if the animation should loop (1 for true, 0 for false).