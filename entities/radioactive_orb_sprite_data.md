---
title: Radioactive Orb Sprite Data
category: entities
---

# Radioactive Orb Sprite Data

This document details the sprite data for the radioactive orb entity in Noita, primarily used by the boss centipede. It defines the visual appearance and animations.

## Sprite Definition

The main `Sprite` element defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/orb_mat_radioactive.png` - The primary image file for the orb.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `fireball` - The animation to play by default.

## Animations

The orb has two defined animations: `fireball` and `detonate`.

### `fireball` Animation

This animation likely represents the orb's active state or projectile form.

*   **name**: `fireball`
*   **pos\_x**: `0`
*   **pos\_y**: `0` - Starts at the top-left of the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in this animation.
*   **frame\_width**: `20` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.05` - Delay between frames in seconds.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally on the sprite sheet.
*   **loop**: `1` - The animation will loop continuously.

### `detonate` Animation

This animation is likely used when the orb is about to explode or is in the process of detonating.

*   **name**: `detonate`
*   **pos\_x**: `0`
*   **pos\_y**: `20` - Starts below the `fireball` animation frames on the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in this animation.
*   **frame\_width**: `20` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.03` - Delay between frames in seconds (faster than `fireball`).
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally on the sprite sheet.
*   **loop**: `1` - The animation will loop continuously.