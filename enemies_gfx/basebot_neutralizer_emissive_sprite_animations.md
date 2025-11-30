---
title: Basebot Neutralizer Emissive Sprite Animations
category: enemies_gfx
---

# Basebot Neutralizer Emissive Sprite Animations

This document details the sprite animations for the `basebot_neutralizer_emissive` enemy in Noita. It focuses on the key attributes of each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/basebot_neutralizer_emissive.png` - The path to the sprite sheet.
*   **offset\_x**: `9` - Horizontal offset for the sprite.
*   **offset\_y**: `15` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played by default.

## Animation States

The following `<RectAnimation>` tags define the different animation states for the Basebot Neutralizer.

### `stand` Animation

*   **name**: `stand`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `6`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.12` - Duration each frame is displayed.
*   **frames\_per\_row**: `8`
*   **loop**: `1` - Indicates the animation loops.

### `walk` Animation

*   **name**: `walk`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **loop**: `1`

### `run` Animation

*   **name**: `run`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **loop**: `1`
*   **Note**: This animation appears to be a copy of the `walk` animation.

### `burn` Animation

*   **name**: `burn`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **loop**: `1`
*   **Note**: This animation also appears to be a copy of the `walk` animation.

### `attack` Animation

*   **name**: `attack`
*   **pos\_x**: `0`
*   **pos\_y**: `40`
*   **frame\_count**: `5`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.05`
*   **frames\_per\_row**: `8`
*   **loop**: `0` - Indicates the animation does not loop.

### `attack_ranged` Animation

*   **name**: `attack_ranged`
*   **pos\_x**: `0`
*   **pos\_y**: `40`
*   **frame\_count**: `5`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.05`
*   **frames\_per\_row**: `8`
*   **loop**: `0`

### `fly_idle` Animation

*   **name**: `fly_idle`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `6`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.085`
*   **frames\_per\_row**: `8`
*   **loop**: `1`

### `fly_move` Animation

*   **name**: `fly_move`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.07`
*   **frames\_per\_row**: `8`
*   **loop**: `1`