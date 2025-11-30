---
title: Barfer Enemy Graphics
category: entities
---

# Barfer Enemy Graphics

This document details the graphical assets and animations for the "Barfer" enemy in Noita.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/barfer.png` - The path to the sprite sheet.
*   **offset\_x**: `9.5` - Horizontal offset for the sprite.
*   **offset\_y**: `15` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation.

### `stand` Animation

*   **name**: `stand`
*   **frame\_count**: `6`
*   **frame\_width**: `18`
*   **frame\_height**: `22`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.1`
*   **pos\_x**: `0`
*   **pos\_y**: `1`

### `walk` Animation

*   **name**: `walk`
*   **frame\_count**: `6`
*   **frame\_width**: `19`
*   **frame\_height**: `23`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.09`
*   **pos\_x**: `0`
*   **pos\_y**: `24`
*   **shrink\_by\_one\_pixel**: `1`

#### Events:

*   **step**: Triggered on frames `2` and `5`. Checks for physics material.

### `run` Animation

*   **name**: `run`
*   **frame\_count**: `6`
*   **frame\_width**: `19`
*   **frame\_height**: `23`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.09`
*   **pos\_x**: `0`
*   **pos\_y**: `24`
*   **shrink\_by\_one\_pixel**: `1`

#### Events:

*   **step**: Triggered on frames `2` and `5`. Checks for physics material.

### `burn` Animation

*   **name**: `burn`
*   **frame\_count**: `6`
*   **frame\_width**: `19`
*   **frame\_height**: `23`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.09`
*   **pos\_x**: `0`
*   **pos\_y**: `24`
*   **shrink\_by\_one\_pixel**: `1`

#### Events:

*   **step**: Triggered on frames `2` and `5`. Checks for physics material.

### `fly_idle` Animation

*   **name**: `fly_idle`
*   **frame\_count**: `4`
*   **frame\_width**: `19`
*   **frame\_height**: `23`
*   **frames\_per\_row**: `15`
*   **frame\_wait**: `0.12`
*   **pos\_x**: `0`
*   **pos\_y**: `47`
*   **shrink\_by\_one\_pixel**: `1`

### `fly_move` Animation

*   **name**: `fly_move`
*   **frame\_count**: `4`
*   **frame\_width**: `18`
*   **frame\_height**: `22`
*   **frames\_per\_row**: `15`
*   **frame\_wait**: `0.12`
*   **pos\_x**: `0`
*   **pos\_y**: `70`

### `attack_ranged` Animation

*   **name**: `attack_ranged`
*   **frame\_count**: `9`
*   **frame\_width**: `19`
*   **frame\_height**: `23`
*   **frames\_per\_row**: `9`
*   **frame\_wait**: `0.08`
*   **pos\_x**: `0`
*   **pos\_y**: `93`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (This animation does not loop)

#### Events:

*   **attack\_spit\_large**: Triggered on frame `3`. Does not check physics material.