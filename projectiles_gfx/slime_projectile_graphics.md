---
title: Slime Projectile Graphics
category: projectiles_gfx
---

# Slime Projectile Graphics

This document details the graphical assets for the "slime" projectile in Noita, as defined in `slime.xml`. It focuses on the sprite and its associated animations.

## Sprite Definition

The main sprite for the slime projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/slime.png` - The path to the image file containing the sprite frames.
*   **default\_animation**: `"spawn"` - The animation that plays by default when the projectile is created.
*   **offset\_x**: `7` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.

## Animations

The projectile utilizes two distinct animations defined by `<RectAnimation>` tags: `fireball` and `spawn`.

### `fireball` Animation

This animation likely represents the projectile in its active flight state.

#### Key Attributes:

*   **name**: `"fireball"`
*   **frame\_count**: `6` - Total number of frames in this animation.
*   **frame\_width**: `15` - Width of each individual frame.
*   **frame\_height**: `13` - Height of each individual frame.
*   **frames\_per\_row**: `6` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.08` - Duration (in seconds) each frame is displayed before transitioning.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that frames should be shrunk by one pixel.

### `spawn` Animation

This animation is the initial visual effect when the projectile is spawned.

#### Key Attributes:

*   **name**: `"spawn"`
*   **frame\_count**: `6` - Total number of frames in this animation.
*   **frame\_width**: `15` - Width of each individual frame.
*   **frame\_height**: `13` - Height of each individual frame.
*   **frames\_per\_row**: `6` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.1` - Duration (in seconds) each frame is displayed before transitioning.
*   **loop**: `0` - This animation does not loop.
*   **next\_animation**: `"fireball"` - After completing, this animation transitions to the `fireball` animation.
*   **pos\_y**: `14` - Vertical position of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that frames should be shrunk by one pixel.