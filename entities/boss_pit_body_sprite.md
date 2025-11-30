---
title: Boss Pit Body Sprite
category: entities
---

---

# Boss Pit Body Sprite

This document describes the sprite and animation data for the Boss Pit entity in Noita.

## Sprite

The main sprite for the Boss Pit is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_pit/boss_pit.png` - Path to the sprite image file.
*   **offset\_x**: `22.5` - Horizontal offset for the sprite.
*   **offset\_y**: `24.5` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

## Animations

The Boss Pit has a "stand" animation defined.

### `stand` Animation:

*   **name**: `stand`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `4` - Total number of frames in the animation.
*   **frame\_width**: `45` - Width of each individual frame.
*   **frame\_height**: `49` - Height of each individual frame.
*   **frame\_wait**: `0.12` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `4` - Number of frames in each row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).