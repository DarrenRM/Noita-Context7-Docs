---
title: Shaman Alt Sprite Animation
category: data/enemies_gfx
---

# Shaman Alt Sprite Animation

This document details the sprite animations for the "shaman_alt" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The core sprite definition for the shaman_alt.

### Key Attributes:

*   **filename**: `data/items_gfx/book_cursed_old` - The base texture file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `18` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

The shaman_alt has several distinct animations, each defined by `RectAnimation`.

### `stand` Animation

The default idle animation.

*   **name**: `stand`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.2` seconds per frame
*   **frames\_per\_row**: `7`
*   **loop**: `1` (loops indefinitely)

### `walk` Animation

The animation for when the enemy is walking.

*   **name**: `walk`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.2` seconds per frame
*   **frames\_per\_row**: `7`
*   **loop**: `1` (loops indefinitely)

### `run` Animation

The animation for when the enemy is running. This is a copy of the `walk` animation.

*   **name**: `run`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.2` seconds per frame
*   **frames\_per\_row**: `7`
*   **loop**: `1` (loops indefinitely)

### `burn` Animation

The animation for when the enemy is burning. This is a copy of the `walk` animation.

*   **name**: `burn`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.2` seconds per frame
*   **frames\_per\_row**: `7`
*   **loop**: `1` (loops indefinitely)

### `attack` Animation

The animation for the enemy's attack.

*   **name**: `attack`
*   **pos\_y**: `20` - This indicates the attack frames are on a different row of the sprite sheet.
*   **frame\_count**: `7`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.07` seconds per frame
*   **frames\_per\_row**: `7`
*   **loop**: `0` (does not loop)

#### `attack` Animation Events

*   **Event**: Triggered at `frame="5"` of the `attack` animation.
    *   **name**: `attack_bite` - The name of the event, likely triggering a bite attack.
    *   **probability**: `1` (always triggers)
    *   **max\_distance**: `500` - Maximum distance for the attack to be effective.
    *   **check\_physics\_material**: `0` - Indicates no specific physics material check is required for this event.
    *   **on\_finished**: `0` - No specific action on animation finish.