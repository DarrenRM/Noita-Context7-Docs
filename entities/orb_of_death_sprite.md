---
title: Orb of Death Sprite
category: entities
---

---

# Orb of Death Sprite

This document describes the sprite and animation data for the "Orb of Death" entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_wizard/orb_death.png` - The path to the sprite image file.
*   **offset_x**: `8` - Horizontal offset for the sprite.
*   **offset_y**: `12` - Vertical offset for the sprite.
*   **default_animation**: `default` - Specifies the name of the default animation to play.

## RectAnimation

The `RectAnimation` element defines a rectangular animation sequence.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame_count**: `6` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual animation frame.
*   **frame_height**: `16` - The height of each individual animation frame.
*   **frame_wait**: `0.09` - The time in seconds to wait between frames.
*   **frames_per_row**: `6` - The number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).