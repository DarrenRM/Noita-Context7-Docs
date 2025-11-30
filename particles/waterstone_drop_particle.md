---
title: Waterstone Drop Particle
category: particles
---

---

# Waterstone Drop Particle

This document describes the `waterstone_drop.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/waterstone_drop.png` - Specifies the texture file for the particle's animation.
*   **offset\_x**: `7` - Horizontal offset for the sprite.
*   **offset\_y**: `7` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: Explosion

The `<RectAnimation>` element defines the "explosion" animation.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `12` - The total number of frames in the animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `14` - The height of each individual frame.
*   **frame\_wait**: `0.06` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `13` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).