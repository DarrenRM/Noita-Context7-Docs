---
title: Pipe Bomb Projectile Graphics
category: projectiles_gfx
---

# Pipe Bomb Projectile Graphics

This document details the graphical assets for the "pipe bomb" projectile in Noita, as defined in `pipe_bomb.xml`.

## Sprite Definition

The main sprite definition for the pipe bomb projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/pipe_bomb.png` - The texture file used for the sprite.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `4.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The animation to play by default.

## Animations

Defines the different visual states and animations for the pipe bomb.

### `fireball` Animation

The primary animation for the projectile while in motion.

#### Key Attributes:

*   **name**: `fireball`
*   **frame\_count**: `6` - Total number of frames in this animation.
*   **frame\_width**: `9` - Width of each individual frame.
*   **frame\_height**: `9` - Height of each individual frame.
*   **frame\_wait**: `1000` - Delay between frames in milliseconds (1 second).
*   **frames\_per\_row**: `6` - Number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates the animation should loop.

### `on_ground` Animation

An animation for when the projectile is on the ground.

#### Key Attributes:

*   **name**: `on_ground`
*   **frame\_count**: `1` - This animation consists of a single frame.
*   **frame\_width**: `9` - Width of the frame.
*   **frame\_height**: `9` - Height of the frame.
*   **frame\_wait**: `0.02` - Very short delay between frames (effectively no delay for a single frame animation).
*   **frames\_per\_row**: `6` - Number of frames arranged horizontally in the texture.
*   **loop**: `0` - Indicates the animation should not loop.