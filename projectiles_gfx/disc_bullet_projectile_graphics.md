---
title: Disc Bullet Projectile Graphics
category: projectiles_gfx
---

# Disc Bullet Projectile Graphics

This document details the graphical assets and animations for the "disc_bullet" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite definition for the disc bullet.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/disc_bullet.png` - The texture file used for the projectile.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `4.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The animation to play by default.

## Animations

Defines the different animation sequences for the projectile.

### `fireball` Animation

The primary firing animation.

#### Key Attributes:

*   **name**: `fireball`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `4` - Total number of frames in this animation.
*   **frame\_width**: `9` - Width of each individual frame.
*   **frame\_height**: `9` - Height of each individual frame.
*   **frame\_wait**: `1000` - Delay between frames in milliseconds.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation should loop (1 for true, 0 for false).

### `on_ground` Animation

An animation played when the projectile lands or is on the ground.

#### Key Attributes:

*   **name**: `on_ground`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in this animation.
*   **frame\_width**: `9` - Width of each individual frame.
*   **frame\_height**: `9` - Height of each individual frame.
*   **frame\_wait**: `0.02` - Delay between frames in seconds.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates the animation should not loop (0 for false).