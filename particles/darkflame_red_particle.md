---
title: Darkflame Red Particle
category: particles
---

---

# Darkflame Red Particle

This documentation describes the `darkflame_red.xml` particle definition, used for creating a red darkflame effect in Noita.

## Sprite Definition

The primary visual representation of the particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/darkflame_red.png` - Specifies the image file used for the particle's sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - Sets the default animation to play when the particle is spawned.

## Animation: Explosion

The `<RectAnimation>` tag defines the "explosion" animation used by the sprite.

### Key Attributes:

*   **name**: `explosion` - The name of this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual animation frame.
*   **frame\_height**: `12` - The height of each individual animation frame.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `7` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation should not loop (it plays once).