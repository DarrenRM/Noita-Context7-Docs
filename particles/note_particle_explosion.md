---
title: Note Particle (Explosion)
category: particles
---

---

# Note Particle (Explosion)

This documentation describes a particle effect in Noita, specifically a small, explosive note-like particle.

## Sprite

The primary visual representation of the particle.

### Key Attributes:

*   **filename**: `data/particles/note_2.png` - The texture file used for the sprite.
*   **offset\_x**: `4` - Horizontal offset for the sprite.
*   **offset\_y**: `4` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The default animation to play for this sprite.

## RectAnimation: `explosion`

Defines the animation sequence for the `explosion` state.

### Key Attributes:

*   **name**: `explosion` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `8` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).

This animation describes a single, static frame, suggesting a brief, sharp visual effect.