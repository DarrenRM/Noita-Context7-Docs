---
title: Lavashot Projectile Sprite
category: projectiles_gfx
---

# Lavashot Projectile Sprite

This document details the sprite and animation definitions for the "lavashot" projectile in Noita.

## Sprite Definition

The main `Sprite` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/lavashot.png` - The path to the sprite sheet.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"spawn"` - The animation to play by default when the projectile is created.

## Animations

The `Sprite` element contains one or more `RectAnimation` elements, defining different animation sequences.

### Animation: `fireball`

This animation likely represents the main visual loop of the projectile in flight.

#### Key Attributes:

*   **name**: `"fireball"`
*   **pos\_x**: `"0"` - Starting X coordinate within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - Starting Y coordinate within the sprite sheet for this animation.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"24"` - The width of each individual frame.
*   **frame\_height**: `"24"` - The height of each individual frame.
*   **frame\_wait**: `"0.10"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"4"` - How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that this animation should loop indefinitely.

### Animation: `spawn`

This animation is designated as the default and likely plays when the projectile is first created.

#### Key Attributes:

*   **name**: `"spawn"`
*   **pos\_x**: `"0"` - Starting X coordinate within the sprite sheet for this animation.
*   **pos\_y**: `"24"` - Starting Y coordinate within the sprite sheet for this animation.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"24"` - The width of each individual frame.
*   **frame\_height**: `"24"` - The height of each individual frame.
*   **frame\_wait**: `"0.02"` - The duration (in seconds) each frame is displayed. This is much faster than the `fireball` animation, suggesting a quick visual effect.
*   **frames\_per\_row**: `"4"` - How many frames are arranged horizontally in the sprite sheet.
*   **next\_animation**: `"fireball"` - After this animation completes, it will transition to the `fireball` animation.
*   **loop**: `"0"` - Indicates that this animation should play only once.