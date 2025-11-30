---
title: Mine Enemy Graphics
category: entities
---

# Mine Enemy Graphics

This document details the graphical assets and animations for the "Mine" enemy in Noita, as defined in `mine.xml`.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the Mine enemy.

### Key Attributes:

*   **filename**: `data/enemies_gfx/mine.png` - The primary image file for the Mine.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `8` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animations

The Mine enemy utilizes two primary animations: `stand` and `detonate`.

### `stand` Animation

This animation represents the Mine in its idle state.

*   **name**: `"stand"`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `1` - Only one frame for the standing animation.
*   **frame\_width**: `12` - Width of each frame.
*   **frame\_height**: `12` - Height of each frame.
*   **frame\_wait**: `0.16` - Duration each frame is displayed.
*   **frames\_per\_row**: `8` - How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` - The animation will loop continuously.

### `detonate` Animation

This animation plays when the Mine is about to explode.

*   **name**: `"detonate"`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `8` - The animation consists of 8 frames.
*   **frame\_width**: `12` - Width of each frame.
*   **frame\_height**: `12` - Height of each frame.
*   **frame\_wait**: `0.09` - Duration each frame is displayed, creating a faster animation for detonation.
*   **frames\_per\_row**: `8` - How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` - The animation will loop continuously.

#### Events within `detonate` Animation:

The `detonate` animation includes specific events triggered at certain frames.

| Frame | Event Name | Probability | Check Physics Material |
| :---- | :--------- | :---------- | :--------------------- |
| 0     | `beep`     | 1           | 0                      |
| 2     | `beep`     | 1           | 0                      |
| 3     | `beep`     | 1           | 0                      |
| 4     | `beep`     | 1           | 0                      |

These events likely correspond to sound effects or visual cues associated with the detonation sequence.