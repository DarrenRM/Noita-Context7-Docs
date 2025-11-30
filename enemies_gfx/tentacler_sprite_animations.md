---
title: Tentacler Sprite Animations
category: enemies_gfx
---

# Tentacler Sprite Animations

This document details the sprite animations for the Tentacler enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

*   **filename**: `data/enemies_gfx/tentacler.png` - The primary image file for the Tentacler.
*   **offset\_x**: `14` - Horizontal offset for the sprite.
*   **offset\_y**: `25` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played by default.

## Animations

Each `<RectAnimation>` tag defines a specific animation sequence.

### `stand` Animation

*   **name**: `stand`
*   **frame\_count**: `6`
*   **frame\_width**: `29`
*   **frame\_height**: `28`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **has\_offset**: `1`
*   **offset\_x**: `14`
*   **offset\_y**: `25`

### `walk` Animation

*   **name**: `walk`
*   **frame\_count**: `6`
*   **frame\_width**: `30`
*   **frame\_height**: `29`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **has\_offset**: `1`
*   **offset\_x**: `14`
*   **offset\_y**: `25`
*   **pos\_y**: `30`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `step` at frame `0` and `3`.

### `run` Animation

*   **name**: `run`
*   **frame\_count**: `6`
*   **frame\_width**: `30`
*   **frame\_height**: `29`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **has\_offset**: `1`
*   **offset\_x**: `14`
*   **offset\_y**: `25`
*   **pos\_y**: `30`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `step` at frame `0` and `3`.

### `burn` Animation

*   **name**: `burn`
*   **frame\_count**: `6`
*   **frame\_width**: `30`
*   **frame\_height**: `29`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **has\_offset**: `1`
*   **offset\_x**: `14`
*   **offset\_y**: `25`
*   **pos\_y**: `30`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `step` at frame `0` and `3`.

### `fly_move` Animation

*   **name**: `fly_move`
*   **frame\_count**: `6`
*   **frame\_width**: `30`
*   **frame\_height**: `29`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **has\_offset**: `1`
*   **offset\_x**: `14`
*   **offset\_y**: `20`
*   **pos\_y**: `59`
*   **shrink\_by\_one\_pixel**: `1`

### `fly_idle` Animation

*   **name**: `fly_idle`
*   **frame\_count**: `6`
*   **frame\_width**: `30`
*   **frame\_height**: `29`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **has\_offset**: `1`
*   **offset\_x**: `14`
*   **offset\_y**: `20`
*   **pos\_y**: `59`
*   **shrink\_by\_one\_pixel**: `1`

### `attack_ranged` Animation

*   **name**: `attack_ranged`
*   **frame\_count**: `6`
*   **frame\_width**: `30`
*   **frame\_height**: `29`
*   **frame\_wait**: `0.07`
*   **frames\_per\_row**: `10`
*   **has\_offset**: `1`
*   **loop**: `0` (This animation does not loop)
*   **offset\_x**: `14`
*   **offset\_y**: `20`
*   **pos\_y**: `88`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `shoot_tentacle` at frame `4`.

### `attack` Animation

*   **name**: `attack`
*   **frame\_count**: `6`
*   **frame\_width**: `30`
*   **frame\_height**: `29`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **has\_offset**: `1`
*   **loop**: `0` (This animation does not loop)
*   **offset\_x**: `14`
*   **offset\_y**: `20`
*   **pos\_y**: `88`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `hit` at frame `4`.

### `attack_stone` Animation

*   **name**: `attack_stone`
*   **frame\_count**: `7`
*   **frame\_width**: `29`
*   **frame\_height**: `28`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `10`
*   **has\_offset**: `1`
*   **loop**: `0` (This animation does not loop)
*   **offset\_x**: `14`
*   **offset\_y**: `20`
*   **pos\_y**: `117`
*   **Events**:
    *   `shoot_ice` at frame `4`.