---
title: Ghoul Sprite Animations
category: entities_gfx
---

# Ghoul Sprite Animations

This document details the sprite animations for the Ghoul enemy in Noita, focusing on key attributes for modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

*   **filename**: `data/enemies_gfx/ghoul.png` - The texture file for the Ghoul.
*   **offset\_x**: `7` - Horizontal offset of the sprite.
*   **offset\_y**: `12` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation played when the Ghoul is idle.

## Animations

Each `<RectAnimation>` tag defines a specific animation sequence.

### `stand` Animation

*   **name**: `stand`
*   **frame\_count**: `6`
*   **frame\_width**: `14`
*   **frame\_height**: `16`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.14` - Duration each frame is displayed.
*   **pos\_x**: `0`
*   **pos\_y**: `1` - Starting Y coordinate for this animation strip.

### `walk` Animation

*   **name**: `walk`
*   **frame\_count**: `6`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.12`
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1` - Indicates a slight reduction in sprite size.

#### Events for `walk`

| Frame | Name     | Probability | Check Physics Material |
| :---- | :------- | :---------- | :--------------------- |
| 2     | `step`   | 1           | 1                      |
| 5     | `step`   | 1           | 1                      |

### `run` Animation

*   **name**: `run`
*   **frame\_count**: `6`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.1`
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1`

#### Events for `run`

| Frame | Name     | Probability | Check Physics Material |
| :---- | :------- | :---------- | :--------------------- |
| 2     | `step`   | 1           | 1                      |
| 5     | `step`   | 1           | 1                      |

### `burn` Animation

*   **name**: `burn`
*   **frame\_count**: `6`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.09`
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1`

#### Events for `burn`

| Frame | Name     | Probability | Check Physics Material |
| :---- | :------- | :---------- | :--------------------- |
| 2     | `step`   | 1           | 1                      |
| 5     | `step`   | 1           | 1                      |

### `jump_up` Animation

*   **name**: `jump_up`
*   **frame\_count**: `1`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.1`
*   **loop**: `0` - This animation does not loop.
*   **pos\_x**: `0`
*   **pos\_y**: `35`
*   **shrink\_by\_one\_pixel**: `1`

#### Events for `jump_up`

| Frame | Name  | Probability | Check Physics Material |
| :---- | :---- | :---------- | :--------------------- |
| 0     | `jump` | 1           | 1                      |

### `jump_fall` Animation

*   **name**: `jump_fall`
*   **frame\_count**: `1`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.1`
*   **loop**: `0` - This animation does not loop.
*   **pos\_x**: `0`
*   **pos\_y**: `52`
*   **shrink\_by\_one\_pixel**: `1`

### `attack_ranged` Animation

*   **name**: `attack_ranged`
*   **frame\_count**: `5`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.1`
*   **loop**: `0` - This animation does not loop.
*   **pos\_x**: `0`
*   **pos\_y**: `69`
*   **shrink\_by\_one\_pixel**: `1`

#### Events for `attack_ranged`

| Frame | Name       | Probability | Check Physics Material |
| :---- | :--------- | :---------- | :--------------------- |
| 3     | `spit_slime` | 1           | 0                      |