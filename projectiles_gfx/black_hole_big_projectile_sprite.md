---
title: Black Hole Big Projectile Sprite
category: projectiles_gfx
---

# Black Hole Big Projectile Sprite

This document details the sprite information for the "black_hole_big" projectile in Noita, focusing on its visual representation and animations.

## Sprite Definition

The main `<Sprite>` element defines the base image and default animation for the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/black_hole_big.png` - The path to the sprite sheet image.
*   **offset\_x**: `48` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `48` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"spawn"` - The animation to play by default when the projectile is created.

## Animations

The projectile utilizes two distinct animations: "fireball" and "spawn".

### Animation: `fireball`

This animation likely represents the active state of the black hole projectile.

#### Key Attributes:

*   **name**: `"fireball"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"32"` - Total number of frames in this animation.
*   **frame\_width**: `"96"` - Width of each individual frame.
*   **frame\_height**: `"96"` - Height of each individual frame.
*   **frame\_wait**: `"0.05"` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `"47"` - Number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `"1"` - Indicates that this animation should loop indefinitely.

### Animation: `spawn`

This animation is designated as the initial visual effect when the projectile is spawned.

#### Key Attributes:

*   **name**: `"spawn"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"96"` - Starting Y position within the sprite sheet. This indicates it's on a different row than the "fireball" animation.
*   **frame\_count**: `"47"` - Total number of frames in this animation.
*   **frame\_width**: `"96"` - Width of each individual frame.
*   **frame\_height**: `"96"` - Height of each individual frame.
*   **frame\_wait**: `"0.05"` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `"47"` - Number of frames that fit horizontally in a single row of the sprite sheet.
*   **next\_animation**: `"fireball"` - Specifies that after this animation finishes, the "fireball" animation should play.
*   **loop**: `"0"` - Indicates that this animation should not loop.