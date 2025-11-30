---
title: Big Disc Bullet Sprite
category: projectiles_gfx
---

# Big Disc Bullet Sprite

This document describes the sprite data for the "Big Disc Bullet" projectile in Noita. It defines the visual appearance and animations used for this projectile.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/disc_bullet_big.png` - The path to the sprite sheet containing the projectile's graphics.
*   **offset\_x**: `8.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8.5` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"fireball"` - The name of the animation to play by default when the projectile is active.

## Animations

The `<Sprite>` tag contains one or more `<RectAnimation>` tags, each defining a specific animation sequence.

### Animation: `fireball`

This animation is likely used when the projectile is in motion.

#### Key Attributes:

*   **name**: `"fireball"`
*   **pos\_x**: `"0"` - Starting X position on the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position on the sprite sheet.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"17"` - The width of each individual frame.
*   **frame\_height**: `"17"` - The height of each individual frame.
*   **frame\_wait**: `"1000"` - The duration (in milliseconds) each frame is displayed.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally on the sprite sheet.
*   **loop**: `"1"` - Indicates that this animation should loop indefinitely.

### Animation: `on_ground`

This animation is likely used when the projectile has landed or is stationary.

#### Key Attributes:

*   **name**: `"on_ground"`
*   **pos\_x**: `"0"`
*   **pos\_y**: `"0"`
*   **frame\_count**: `"1"` - This animation consists of a single frame.
*   **frame\_width**: `"17"`
*   **frame\_height**: `"17"`
*   **frame\_wait**: `"0.02"` - A very short wait time, suggesting a quick transition or a static pose.
*   **frames\_per\_row**: `"4"`
*   **loop**: `"0"` - Indicates that this animation should not loop.