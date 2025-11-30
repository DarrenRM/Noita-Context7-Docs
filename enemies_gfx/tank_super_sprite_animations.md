---
title: Tank Super Sprite Animations
category: enemies_gfx
---

# Tank Super Sprite Animations

This document details the sprite animations for the "Tank Super" enemy in Noita, as defined in `tank_super.xml`. It focuses on the key attributes of each animation, providing a concise overview for modding purposes.

## Sprite Definition

The main sprite definition for the Tank Super.

### Key Attributes

*   **filename**: `data/enemies_gfx/tank_super.png` - The path to the sprite sheet.
*   **offset\_x**: `9` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

This section breaks down the different animations defined for the Tank Super.

### `stand` Animation

The idle animation for the Tank Super.

*   **name**: `stand`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `1`
*   **frame\_width**: `22`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.16`
*   **frames\_per\_row**: `11`
*   **loop**: `1` (true)

### `walk` Animation

The animation for when the Tank Super is walking.

*   **name**: `walk`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `4`
*   **frame\_width**: `22`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `11`
*   **loop**: `1` (true)

### `run` Animation

The animation for when the Tank Super is running. This is a copy of the `walk` animation with a faster frame wait.

*   **name**: `run`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `4`
*   **frame\_width**: `22`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `11`
*   **loop**: `1` (true)

### `burn` Animation

The animation for when the Tank Super is burning. This is a copy of the `walk` animation with a faster frame wait.

*   **name**: `burn`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `4`
*   **frame\_width**: `22`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `11`
*   **loop**: `1` (true)

### `attack` Animation

The primary attack animation for the Tank Super.

*   **name**: `attack`
*   **pos\_x**: `0`
*   **pos\_y**: `40`
*   **frame\_count**: `4`
*   **frame\_width**: `22`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.07`
*   **frames\_per\_row**: `11`
*   **loop**: `0` (false)
*   **Events**:
    *   Frame `1`: `shoot_bullet`
    *   Frame `3`: `shoot_bullet`

### `attack_ranged` Animation

A ranged attack animation, identical to the `attack` animation.

*   **name**: `attack_ranged`
*   **pos\_x**: `0`
*   **pos\_y**: `40`
*   **frame\_count**: `4`
*   **frame\_width**: `22`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.07`
*   **frames\_per\_row**: `11`
*   **loop**: `0` (false)
*   **Events**:
    *   Frame `1`: `shoot_bullet`
    *   Frame `3`: `shoot_bullet`

### `attack_grenade` Animation

An animation for throwing a grenade.

*   **name**: `attack_grenade`
*   **pos\_x**: `0`
*   **pos\_y**: `60`
*   **frame\_count**: `11`
*   **frame\_width**: `22`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.04`
*   **frames\_per\_row**: `11`
*   **loop**: `0` (false)
*   **Events**:
    *   Frame `8`: `shoot_bullet`