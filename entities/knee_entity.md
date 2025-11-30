---
title: Knee Entity
category: entities
---

# Knee Entity

This document describes the `knee.xml` entity, which appears to be a visual component for a boss or enemy in Noita.

## Sprite

The entity uses a sprite for its visual representation.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_meat/knee.png` - Specifies the texture file for the sprite.
*   **offset\_x**: `3.5` - Horizontal offset for the sprite.
*   **offset\_y**: `3.5` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

### Animations:

#### stand

This animation defines the "stand" state for the knee sprite.

*   **name**: `stand`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `4` - Total number of frames in the animation.
*   **frame\_width**: `7` - Width of each individual frame.
*   **frame\_height**: `7` - Height of each individual frame.
*   **frame\_wait**: `0.1` - Time in seconds each frame is displayed.
*   **frames\_per\_row**: `4` - Number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.